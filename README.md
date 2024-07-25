
# Overview

Consider a situation where a reporter needs to send some secret message to news studio or consider a situation of war where soldier needs to pass some secret information to the base. How will they do ?  
One way they can do is by concealing the message into a non-secret Text, Image, Audio or Video file, that will be later used to extract the message.  

The practice of concealing messages or information within other non-secret data, such as text, image, audio, or video files, to avoid detection is known as **Steganography**. This project facilitates the same. It provides the capability to _hide text message in two different file formats_ i,e. `Text` and `Audio`.

## How to use ?

- Get the repo codes down to your work environment
- Install required python libraries - `tkinter` `os` `numpy` `termcolor` `pyfiglet` `cv2` `pillow` `wave`
- Run any steganography file - `TextStegano.py` `ImageStegano.py` `AudioStegano.py` or `VideoStegano.py`
- All the files that are going to be embed are present in 'sample_files' folder. And after embedding the message output file gets saved in 'Result_files' folder with name as "<file_name>_embeded".
Note that ImageStegHelper.py is a helper file to ImageStegano, that does nothing when compiled. And for embedding in gif use VideoStegno.py
- Note : You would require to **update path** of *Result_files* folder as per your system path. Else it will throw `error` while saving file after embeding, as path where to save will not be found.


## Working Mechanism of Text Steganography

Text steganography involves hiding secret messages within text files by manipulating the text's content while maintaining its readability. This project provides functionalities for both encoding (embedding) and decoding (extracting) secret messages within text files using a combination of encoding techniques and Zero-Width Characters (ZWC).

### Program Components

#### *Encoding*: 

1. Input Acquisition: The user selects a cover text file and provides the message to be encoded.
2. Binary Conversion: Each character of the input message is converted into binary format, and various transformations are applied based on the character's ASCII value.
3. Embedding: The binary representation of the encoded message is embedded into the cover text file using Zero-Width Characters (ZWC). Each ZWC sequence corresponds to a binary bit.
4. Output Generation: The modified text is written to a new text file, which is saved in the specified directory.

#### *Decoding* 

1. Input Acquisition: The user selects the stego text file from which to extract the hidden message.
2. Data Extraction: ZWC sequences are identified and converted back into binary format to reconstruct the encoded message.
3. Character Reconstruction: The binary-encoded characters are transformed back into ASCII characters to obtain the original message.
4. Output Display: The decoded message is displayed to the user.


## Working Mechanism of Audio Steganography

Audio steganography involves embedding and extracting data within audio files without perceptibly altering the audio quality. To embed data, the audio file's binary representation is manipulated by replacing the least significant bits (LSBs) of selected bytes with the binary representation of the secret message. This process subtly modifies the audio data, making it imperceptible to human listeners. 

During extraction, the LSBs of the audio bytes are examined to reconstruct the binary representation of the hidden message. By identifying and decoding the embedded data, the original message can be retrieved without affecting the audio's audible characteristics. This process allows for covert communication through seemingly innocuous audio files, enabling secure transmission of sensitive information while maintaining the integrity of the audio content.

### Program Components

#### *Encoding* 

1. Input Acquisition: The user selects an audio file to encode and inputs the secret message.
2. Data Preparation: The audio file is opened in binary mode, and its frames are read. The frames are then converted into a list of bytes.
3. Message Encoding: The secret message is converted into binary format. A special delimiter (`*^*^*`) is added to mark the end of the message. Each character of the message is encoded into binary format and then embedded into the LSBs of the audio file's byte data.
4. Output Generation: The modified byte data is written back to a new audio file, which is saved in the specified directory.

#### *Decoding*

1. Input Acquisition: The user selects the audio file from which to extract the hidden message.
2. Data Preparation: Similar to the encoding process, the selected audio file's frames are read and converted into byte data.
3. Message Extraction: The LSBs of each byte in the audio data are examined to reconstruct the binary representation of the hidden message. The message extraction continues until the special delimiter (`*^*^*`) is encountered.
4. Output Display: The extracted message is displayed to the user.


## User Interface

The program provides a command-line interface (CLI) for users to perform various file steganography operations. Users can choose between encoding a message into a file or decoding a message from a file. The process continues until the user chooses to exit the program. 

Additionally, the program utilizes the tkinter library in Python to present GUI dialogue boxes for selecting (opening) files, enhancing user convenience.


## Recommended


Use smaller files to perform steganography into as it holds sufficient capability for hiding messsage else it may take longer time to read the input files.


<div> 
<h2 align = 'right'> Thank You !! </h2>
</div>
