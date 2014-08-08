---
layout: product
title: DWrite.dll wrapper
summary: Turns off ClearType in Internet Explorer 9
permalink: /dwrite-dll-wrapper/
---
Are you dissatisfied with Internet Explorer 9's font rendering?

![A screenshot of Internet Explorer 9 with its default font rendering][ie9-original]

Would you instead prefer your fonts be rendered without any anti-aliasing, to look like this?

![A screenshot of Internet Explorer 9 with a more classic font rendering][ie9-aliased]

If so, you have come to the right place!  Copying our dwrite.dll (and accompanying detoured.dll) to a program's folder gives us a chance to intercept and forward the calls to the real DWrite.dll, disabling Font Smoothing in the process.

![The words 'Download' and 'free' in fancy lettering][download]

## How to turn off the blurry fonts for Internet Explorer 9 (32-bit version only)

1. Download DWriteWrapper from the Downloads below.
2. Extract and copy both DLL files to C:\Program Files\Internet Explorer\  You will need administrator rights to do this.
  - **64-bit users**: the path will be C:\Program Files (x86)\Internet Explorer\
3. Close all instances of Internet Explorer and then re-open them.
4. Enjoy the bliss of crisp fonts!

## How to disable ClearType in HtmlHelp (the CHM viewer)

1. Download the attached file.
2. Copy and rename the file C:\Windows\hh.exe to a new folder, say C:\Program Files\HtmlHelp\hh2.exe
  - **64-bit users**: the paths will be C:\Windows\SysWOW64\hh.exe and C:\Program Files (x86)\HtmlHelp\hh2.exe
3. Extract and copy both DLL files next to hh2.exe
4. Find your favorite .chm file (any one will do), right-click on it > Open with > Choose default program...
5. Click Browse... navigate to your shiny new hh2.exe and click Open (or double-click it).
6. Check the checkbox next to Always use the selected program to open this kind of file
7. Click OK
8. Chill out with the straight lines!

## How to replace DirectWrite's "ideal font rendering" effects for any other program that embeds MSHTML.dll (Google Talk, H3Viewer, etc.)

1. Download the DWrite.dll wrapper ZIP file.
2. Extract and copy both DLL files to the same folder as the program executable.
3. Start or restart the program.
4. Smile at the lack of sub-pixel rendering!

## Boring details

This is actually a port of the [Anti-Aliasing Tuner for Firefox 4](https://addons.mozilla.org/en-US/firefox/addon/anti-aliasing-tuner/), minus the ability to customize the options.  To learn how it works, see the article [How to take control of Internet Explorer 9's text rendering](http://blog.softwareninjas.ca/2011/03/how-to-take-control-of-internet.html).  An upcoming release will implement the novel idea of trying to read the options from the operating system's settings and add 64-bit support.  The source code has been published under the [MIT License](http://www.opensource.org/licenses/mit-license.php) at <https://softwareninjas.kilnhg.com/Repo/Open-Source/Group/DWrite-dll-Wrapper>

## Warning: DWrite.dll versions up to 1.4.5 break printing in IE9

A few users have written to report that trying to print from Internet Explorer 9 with the DWrite.dll wrapper installed will crash Internet Explorer.  This bug has been fixed in version 1.4.8.

### Workaround for printing with versions up to 1.4.5

It is still possible to print with the old versions (although you really should upgrade), but it has to be done indirectly, like this:
Open the Print dialog.
Select the "Microsoft XPS Document Writer" device instead of your usual printer.
Adjust any other setting you want.
Click the "Print" button.
A "Save As" dialog will pop up. Select a folder and type in a filename (such as printout.xps) and click "Save".
Open the folder from step 5 and double-click on the XPS file. This should open the XPS Viewer.
Go to File > Print
Select your usual printer and settings and click "Print".

## Downloads

You can download [DWrite-1.4.8.zip](DWrite-1.4.8.zip)

[download]: /images/download.png
[ie9-aliased]: /images/IE9 - aliased.png
[ie9-original]: /images/IE9 - original.png
