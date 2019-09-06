# Crontab



- Copy the python file to /bin:
    
    
`
    sudo cp -i /path/to/your_script.py /bin
`


 - Add A New Cron Job:
 
    
`
    sudo crontab -e
`


 - Scroll to the bottom and add the following line (after all the #'s):


`
    @reboot python3 /.../your_script.py & ( for python scripts)
`    

   or


`
    @reboot /home/pi/dht11/temp.sh (for bash scripts)
`


 - The “&” at the end of the line means the command is run in the background and it won’t stop the system booting up.


 - Test it:


`
    sudo reboot
`

- Make sure that you give the absolute location to files in the scripts you will be running using crontab.

  For example on bash.sh and tempgps.py give full directories to the files you will be writing to/running.
