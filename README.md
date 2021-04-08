
#### DEDSECIMSI is python based tool which use for capturing imsi numbers and sms and also you able to customize your capturing and it's make easy to capture sms and imsi numbers for those who not have much knowledge about gsm packets capturing.

Disclaimer :This program was made to understand how GSM network works. Not for bad hacking ! We are not responsible for any illegal activity !

Setup:

# installation: 
1. git clone https://github.com/0xbitx/dedsecimsi.git
1. sudo apt-get install python-pyshark

# Install Gr GSM : ( For receiving GSM transmissions )
1. sudo add-apt-repository -y ppa:ptrkrysik/gr-gsm
1. sudo apt-get update
1. sudo apt-get install gr-gsm

#### If gr-gsm failled to setup. Than follow those this: https://github.com/ptrkrysik/gr-gsm/wiki/Installation

## Install Kalibrate : ( For finding frequencies )

1. sudo apt install build-essential libtool automake autoconf librtlsdr-dev libfftw3-dev
2. git clone https://github.com/steve-m/kalibrate-rtl
3. cd kalibrate-rtl
4. ./bootstrap && CXXFLAGS='-W -Wall -O3'
5. ./configure
6. make
7. sudo make install

## USAGE:

#### You need gsm frequency on which you capture sms or imsi. By using kalibrate you will get all your near gsm base stations frequencies.

kal -s GSM900

#### kal: Scanning for GSM-900 base stations.

##### GSM-900:

#### chan: 4 (935.8MHz + 320Hz)	power: 1829406.95

#### chan: 11 (937.2MHz + 308Hz)	power: 4540354.88

#### Now you need to capture gsm traffic using gr-gsm on frequency of your any gsm base station which you get from kalibrate.

grgsm_livemon -f <your_frequency>M

#### EXAMPLE:

1. grgsm_livemon -f 935.8M

##### if you see output that's mean you getting gsm packets than continue other setps else change frequency.

2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b

2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b

2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b

2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b 2b

#### Now every thing is ready you can start now capturing sms or imsi numbers using gsmevil. You able to run imsi catcher and sms sniffer both at same time using 2 seprate terminal for capture imsi numbers and sms both at same time.

1. cd <your dedsecimsi folder> #Example cd dedsecimsi
  
  ## Capturing IMSI :
  
  #### Run this command to quick start imsi capturing.
  
  1. python imsi.py

# options:

1. python imsi.py -h                                                                                           

Usage: imsi.py: [options]

Options:

-h, --help            show this help message and exit

-i IFACE, --iface=IFACE  Interface (default : lo)

-p PORT, --port=PORT  Port (default : 4729)

-m IMSI, --imsi=IMSI  IMSI to track (default : None, Example: 123456789101112)

-s SAVE, --save=SAVE  Save all imsi numbers to sqlite file. (default : None)

#### For save all imsi numbers with details in sqlite file.(It's will show you output on screen and also save in file)

1. python imsi.py -s example.db

#### For capture only specific imsi. (It's will show you only your given imsi result)

1. python imsi.py -m imsi_here (Example: python imsi.py -m 123456789101112)

 ## Capturing SMS :
#### Run this command to quick start sms capturing.

1. python sms.py

# Options :

1. python sms.py -h                                                                                           

Usage: sms.py: [options]

Options:

-h, --help                show this help message and exit

-i IFACE, --iface=IFACE   Interface (default : lo)

-p PORT, --port=PORT      Port (default : 4729)

-n NUMBER, --number=NUMBER  Phone number (default : None)

-s SAVE, --save=SAVE  Save all text messages to sqlite file. (default: None)

#### For save all sms in sqlite file.(It's will show you output on screen and also save in file)

1. python sms.py -s example.db

#### For capture only specific phone number sms. (It's will show you only your given phone number result)

1. python sms.py -n phone_number_here (Example: python SmsEvil.py -n 09095676722)


# Requirements:

linux operating system (kali linux) rtl-sdr (RTL2832U) with antenna

rtl-sdr device available on lazada:

name of product: RTL-SDR Blog RTL SDR V3 R820T2 RTL2832U 1PPM TCXO SMA RTLSDR Software Receiver Defined Radio

# Contact:
Email :0xbit25125@gmail.com

# Thanks to YAHAWAH
