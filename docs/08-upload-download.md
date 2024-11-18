


# File Upload and Download


\begin{center}\includegraphics[width=0.8\linewidth]{resources/images/08-upload-download_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_252} \end{center}

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


\begin{center}\includegraphics[width=1\linewidth]{resources/images/08-upload-download_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g16e400fe3e8_0_0} \end{center}

<div class = "warning">
Note that the version of Cyberduck in the Software Center or Self Service might not be current, causing compatibility issues with some operating systems.
</div>

## Create Connection

Launch Cyberduck and click on "Open Connection".

- From the dropdown menu, select "SFTP (SSH File Transfer Protocol)"
- For Server, type "rhino.fhcrc.org"
- Fill in your HutchNetID for Username and fill in your password

Click "Connect"


\includegraphics[width=1\linewidth]{resources/images/08-upload-download_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g1579ffd7b01_12_28} 

Click "Allow". You can also check the box to indicate "Always".


\includegraphics[width=1\linewidth]{resources/images/08-upload-download_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g1579ffd7b01_12_33} 

You should see your script file "`01.sh`" and the log file.


\includegraphics[width=1\linewidth]{resources/images/08-upload-download_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g1579ffd7b01_12_37} 

## Download and Edit the Script

- Right click on "`01.sh`" and select "Download"
- You will see a "Transfers" prompt open, and the `01.sh` file should now appear in your Downloads folder
- Open the `01.sh` in your Downloads folder


\includegraphics[width=1\linewidth]{resources/images/08-upload-download_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g1579ffd7b01_12_41} 

Edit the message to include your name and save the file. Rename the file `01-name.sh`.


\includegraphics[width=1\linewidth]{resources/images/08-upload-download_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g1579ffd7b01_12_45} 

## Upload the New Script

From your Downloads folder, simply drag the file to Cyberduck.
  

\includegraphics[width=1\linewidth]{resources/images/08-upload-download_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g1579ffd7b01_12_49} 

You should now see the new script among your cluster files.


\includegraphics[width=1\linewidth]{resources/images/08-upload-download_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g15cf3fa00a4_0_6} 

## Run the New Script

Return to your Terminal. Submit a job with your new script by running the following. When you type `ls` you should see a new log file! 

```
sbatch 01-name.sh
```


\includegraphics[width=1\linewidth]{resources/images/08-upload-download_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_0} 

<div class = "notice">
The job numbers included in log file names generally increase in number. The greater the number, the more recently the job was run.
</div>

Use the `cat` command to inspect the log. Make sure you replace `[your-number-here]` to match your file. The message should show the new text that you added!

```
cat slurm-[your-number-here].out
```


\includegraphics[width=1\linewidth]{resources/images/08-upload-download_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_6} 
