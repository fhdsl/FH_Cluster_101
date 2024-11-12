


# File Upload and Download

<img src="resources/images/06-upload-download_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_252.png" alt="We are on the sixth step of the pathway." width="80%" style="display: block; margin: auto;" />

Exchanging files with the cluster is very important. You can imagine scenarios where:

- You want to download log files or output files
- You want to upload a custom `.sh` script file that you wrote on your laptop
- You want to upload other files

In this course, upload and download of files is performed using [Cyberduck](https://cyberduck.io/){target="_blank"}. Cyberduck is a tool that lets us connect to the cluster securely, browse files, and transfer files securely.

<div class = "warning">
If you are working with sensitive data (such as data with [PHI](https://www.hhs.gov/answers/hipaa/what-is-phi/index.html){target="_blank"} that requires [HIPAA compliance](https://www.hhs.gov/hipaa/index.html){target="_blank"}, you need to be extra cautious about transferring your data to the cluster. Your home directory is not an appropriate storage option for such data. Make sure you consider any stipulations in your data use agreements.
</div>

## Download Cyberduck

Download the latest version of Cyberduck [here](https://cyberduck.io/download/){target="_blank"}.

<img src="resources/images/06-upload-download_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g16e400fe3e8_0_0.png" alt="Downloads page for Cyberduck." width="100%" style="display: block; margin: auto;" />

<div class = "warning">
Note that the version of Cyberduck in the Software Center or Self Service might not be current, causing compatibility issues with some operating systems.
</div>

## Create Connection

Launch Cyberduck and click on "Open Connection".

- From the dropdown menu, select "SFTP (SSH File Transfer Protocol)"
- For Server, type "rhino.fhcrc.org"
- Fill in your HutchNetID for Username and fill in your password

Click "Connect"

<img src="resources/images/06-upload-download_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g1579ffd7b01_12_28.png" alt="Screenshot of Cyberduck “Open Connection” configuration." width="100%" />

Click "Allow". You can also check the box to indicate "Always".

<img src="resources/images/06-upload-download_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g1579ffd7b01_12_33.png" alt="You can select allow when Cyberduck asks about an Unknown Fingerprint." width="100%" />

You should see your script file "`01.sh`" and the log file.

<img src="resources/images/06-upload-download_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g1579ffd7b01_12_37.png" alt="Files, including the script we previously ran, can be accessed via Cyberduck." width="100%" />

## Download and Edit the Script

- Right click on "`01.sh`" and select "Download"
- You will see a "Transfers" prompt open, and the `01.sh` file should now appear in your Downloads folder
- Open the `01.sh` in your Downloads folder

<img src="resources/images/06-upload-download_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g1579ffd7b01_12_41.png" alt="Screenshot of the script opened on the users local laptop." width="100%" />

Edit the message to include your name and save the file. Rename the file `01-name.sh`.

<img src="resources/images/06-upload-download_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g1579ffd7b01_12_45.png" alt="Screenshot of the edited and renamed script file contents. The contents of the script now reads &quot;Hello, Ava!&quot;." width="100%" />

## Upload the New Script

From your Downloads folder, simply drag the file to Cyberduck.
  
<img src="resources/images/06-upload-download_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g1579ffd7b01_12_49.png" alt="Screenshot of local and Cyberduck files, depicting the dragging that transfers the file over." width="100%" />

You should now see the new script among your cluster files.

<img src="resources/images/06-upload-download_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g15cf3fa00a4_0_6.png" alt="The new file is now listed in Cyberduck and is therefore on the cluster." width="100%" />

## Run the New Script

Return to your Terminal. Submit a job with your new script by running the following. When you type `ls` you should see a new log file! 

```
sbatch 01-name.sh
```

<img src="resources/images/06-upload-download_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_0.png" alt="After running the newly edited script, there is a new log file present on the cluster." width="100%" />

<div class = "notice">
The job numbers included in log file names generally increase in number. The greater the number, the more recently the job was run.
</div>

Use the `cat` command to inspect the log. Make sure you replace `[your-number-here]` to match your file. The message should show the new text that you added!

```
cat slurm-[your-number-here].out
```

<img src="resources/images/06-upload-download_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_6.png" alt="The message &quot;Hello, Ava!&quot; has been printed to the Terminal using the cat command." width="100%" />
