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
    @reboot python3 /.../your_script.py &
`    

   or

`

    @reboot /home/pi/dht11/temp.sh

`


 - The “&” at the end of the line means the command is run in the background and it won’t stop the system booting up.


 - Test it:


`
    sudo reboot
`
