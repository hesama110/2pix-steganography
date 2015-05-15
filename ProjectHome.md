# 2pix Steganography #

## Description ##

2Pix integrates with Windows to allow you to easily encrypt and hide files in bitmap images, a process called steganography (not to be confused with stenography). Data is stored in the low-order bits of each pixel of an image, so the file is completely hidden from view. Version 1.1 now provides plausible deniability because no unencrypted signature is stored in the [image header](http://2pix-steganography.googlecode.com/svn/trunk/ScottClayton.Stenography.2pix/TP_File.cs). It should be impossible to prove an image contains a hidden file (if you use a strong password and only use 1 or 2 bits per pixel component).

## Features ##

  * Integration into the right-click menu in Windows
  * Encrypts files using 256 bit Rinjdael (AES) before hiding them
  * Secretly hides any file **inside** a bitmap image's low order bits
  * Plausible Deniability (impossible to prove and image contains a hidden file)

## How Does it Work? ##

There are 8 bits per pixel in a standard bitmap image. The more of those bits we use to store data in an image, the lower the resulting quality of the image will be. Although you can store several times more information per image when using more bits per pixel, it is a good idea to use as few (ideally just one) bit per pixel so that the color change is imperceptible.

Below is an image illustrating what the resulting encoded images would look like at each encoding level after being encoded with the same 70KB file. Note that the original image was a black and white picture of a QR code--the big black dots are not the information being encoded into the image. **See the Examples section below for a real life example.**

![http://2pix-steganography.googlecode.com/svn/trunk/Example/sizes60.png](http://2pix-steganography.googlecode.com/svn/trunk/Example/sizes60.png)

There is also some useful information about steganography at [Wikipedia](http://en.wikipedia.org/wiki/Steganography).

## Screenshots ##

The main window:

![http://2pix-steganography.googlecode.com/svn/trunk/Screenshots/mainwindow.png](http://2pix-steganography.googlecode.com/svn/trunk/Screenshots/mainwindow.png)

![http://2pix-steganography.googlecode.com/svn/trunk/Screenshots/encoder.png](http://2pix-steganography.googlecode.com/svn/trunk/Screenshots/encoder.png)

![http://2pix-steganography.googlecode.com/svn/trunk/Screenshots/decoder.png](http://2pix-steganography.googlecode.com/svn/trunk/Screenshots/decoder.png)

Window's right-click integration for bitmap images:

![http://2pix-steganography.googlecode.com/svn/trunk/Screenshots/Extracting.jpg](http://2pix-steganography.googlecode.com/svn/trunk/Screenshots/Extracting.jpg)

![http://2pix-steganography.googlecode.com/svn/trunk/Screenshots/Decrypting.jpg](http://2pix-steganography.googlecode.com/svn/trunk/Screenshots/Decrypting.jpg)

## Example ##

Below is a link to an image that contains the entire 35KB license.txt file. You can download it from the repository or directly using the link below. **Note**, however, that the image you see below is a PNG, not the BMP you need to download. If you download the PNG version (by right clicking) then you will not be able to extract any files. Again, **you must download the version linked to, not the one shown**.

The password to extract the file is **2pix**.

[Download Sample Image](http://2pix-steganography.googlecode.com/svn/trunk/sample.bmp)

Here is what the image looks like:

![http://2pix-steganography.googlecode.com/svn/trunk/Example/sample.png](http://2pix-steganography.googlecode.com/svn/trunk/Example/sample.png)

Thanks to [Alvesgaspar](http://commons.wikimedia.org/wiki/File:Moscow_July_2011-34a.jpg) who took this photo!

## Advice ##

Make sure that you use a strong password (alpha-numeric and at the very least 10 characters long) and only one bit per pixel encoding so that even if an attacker is made known of the existence of a hidden file in an image, he will have to brute force the password before he can gain access. Remember that you use this software at your own risk, so be smart about how you store sensitive information.

## Other Links ##

If you like 2pix, or just security in general, try out these other links:

  * My [CAPTCHA Breaking Scripting Language](http://code.google.com/p/captcha-breaking-library/) project
  * My article on how to [Encrypt Communication between C# and PHP](http://www.codeproject.com/Articles/223081/Encrypting-Communication-between-Csharp-and-PHP)

And here are some programs I use often and really like:

  * [TrueCrypt](http://www.truecrypt.org/) - Open-source on-the-fly drive encryption.
  * [KeePass](http://keepass.info/) - An excellent way to secure your many passwords.

## Troubleshooting ##

If you are having problems installing the right-click option, see [installing the right-click option in Windows](InstallingRightClick.md).

## License ##

The software and source code is released under the GPL version 3 and is Copyright Scott Clayton 2010-2012.

## Transfer ##

This project was transferred from Source Forge on June 16, 2012.