# Want to modify or edit ASIC miner firmware?
## Or even create your own firmware?
<p>
First thing we need to do is to apply our changes into the .img .bin, etc. file that we use to upgrade/downgrade our ASIC miner firmware. Then you can even create your own firmware, reskin, fix issues, change logos, change pool by upgrading, and tons of other things.<br>
<br>
<strong>
But how to extract the .img file? Apply our changes? and finally repack it back into .img file, boot it on ASIC miner and change its firmware into something desirable that we wanted?
</strong>
<br>
Here is a set of tools I used to solve ASIC miner's control board related challenges. Including unpacking, editing, and repacking the image file used to upgrade/downgrade and boot the control board firmware.<br> I actually want to modify the firmware as I desire, change web/user interface logo, change languages, and do tons of other interesting hacks.
</p>

## Documentation
<p>
This doc is written to help us if we forget how to unpack and repack Whatsminer image (.img) files.<br>
These .img files are actual software/firmware that runs the ASIC miner.<br>
These instructions are gathered with deep research, googling and I thought they might be forgotten and also be useful for others, so I have shared it here for everyone.
</p>

### Problem identification:
<p>
I want to unpack Whatsminer ASIC device image file, then edit some file inside it, and finally repack it as .img file.
This .img file will then written to a SD card using PhoenixCard application and booted on Whatsminer control board.
The entire system and functionality of the OS, etc. is defined inside the image file, this applies even to the web interface of the ASIC miner, logos, user interface design, hardware functionality, etc.
</p>

<p>
So with unpacking an image, editing its programs, and repacking it back to .img type file I can change how the ASIC miner functions and actually a lot more beyond the researches that I have done. 
</p>

#### So, here are my approaches:
(approaches to actually change how an ASIC miner works)
<ol>

<li>
I first used a tool on windows called R-Studio recovery tool, but it was not a free software, thus I decided to leave it. <br>
I even tried to use soft98.ir or p30download.ir, to download a free software or something similar to unpack, repack my stuff but they all failed to provide me with an appropriate tool.
</li><br>

<li>
Then I used Binwalk on Linux to extract (Unpack the data from Whatsminer image) with the following command:
$ binwalk -e path-to-image-to-extract.img
the problem with this approach is that I could not find a suitable way to repack it as image file once I have made changes.
Binwalk will gives us a directory with multiple duplicated files and folders with deep hierarchy which is somehow not possible to repack this hierarchy as an .img file.
</li><br>

<li>
I used Android Kitchen to do all the procedures but not useful since the filesystem is not the same as what Android Kitchen requires.
URL to Android Kitchen: https://github.com/dsixda/Android-Kitchen/
</li><br>

<li>
So, after many days trying and researching, I found a new tool called "imgRePacker_206". This tool was some how promising at first but
later it throws error at my face like the other tools. So what I done was:<br>
Download the imgRePacker_206 from my Github: https://github.com/AhmadVakil/Image-file-tools <br>
Drag and drop the .img file inside the CMD area (As it requires), get the .img file extracted in a directory very nice, but unfortunately when I
modify the extracted .img directory and drag and drop back the modified directory I get many errors.<br> I am not going to write these errors here
so you can try it your self. But remember these errors caused by version 206 or "imgRePacker_206".
</li><br>

<li>
The previous tool ("imgRePacker_206") that I have suggested was not working as it should, then I have changed the version to 203 which is "imgRePacker_203" 
and it is working well with both unpacking and repacking of Whatsminer image file.
</li><br>

</ol>

<p>
Note: In all of this explanations, I used the image called "WhatsMiner-SDCard-Burn-Image-H3-20171128.18.2.img". 
I have not checked with other .img files but they should work just fine with one of the tools I offered in the mentioned Git repository.
You can get the file from https://megaminer.net/download/asic/whatsminer-firmware-download/
</p>

<strong>
Good luck and let me know if you need help by dropping an issue.<br>
I will update this doc as I research more.
</strong>

