# Beat Extraction

The purpose of this program is to extract a text file which contains the location (timestamp) of the beats in a song file.

This text file can be used in the Beat Saber game (under development) by the Dev Club - IITD.

## Steps to produce the timestamp file

1) Install aubio library in linux (can use WSL) :
    
    #### sudo apt-get install python3-aubio python-aubio aubio-tools

    Official site:  https://aubio.org/

2) (OPTIONAL) Pre-process the audio file using Audacity (Can be worked on further):

    a) split the track to mono.
    
    b) effect -> invert : on one of the tracks.

    c) select both the tracks.

    d) effect -> normalise.  Normalise peak amplitude set to -10 dB.

    e) effect -> change bass and treble .

    f) increase both bass and treble considerably. Bass should be greater than treble for best results.

    ** this step needs to be worked on.

3) Check if aubio is working by running 'aubio --help' in terminal.

4) Put program<i></i>.sh in the same directory as that of the song file and rename the song as song.mp3.

5) Run the shell script in terminal.

    ** Can also run this command from terminal :

    aubio beat -i './song.mp3' -H 1024 > tempo.txt

    ** Can alter hop size '-H number' reduce 1024 for fast songs (increases difficulty).

6) tempo.txt will be generated with the timestamps.


### **Can also use aubiotrack library (program2.<i></i>sh)

It has more options.

Run this: 

aubiotrack -i './song.mp3' -H 1024 -t 0.1 -s -100 > tempo.txt --onset hfc

aubiotrack --help  :for documentation.