# Rusty's Lab

Rusty's Lab builds scanners for microscopic images. They need you to write the software for managing the files. The good news is their scanners are shipped with a fully featured microprocessor, and a full linux suite available, so the software that you'll be writing will be able to be written and tested on your desktop machine and then built on their scanners or whatever.

As of right now, we need a file type for our scanners that can hold the images. The scanner firmware will write RGB bytes to a file, which your program must wrap in relevant data, and can be modified as necessary. Here's what you need to deliver:

* Create a program that can take a bunch of bytes represented as RGB bytes to a file and output a file with these parameters:
	* The file type starts with the bytes RLI, standing for "Rusty's Lab Image"
	* The file uses ASCII for everything
	* After the opening bytes, a header with key value pairs has the following information:
		* Date and time file created in the format dd/mm/yy
		* What version of the library was used to generate the file following semantic versioning
		* Dimensions of the file in pixels, width by height, each as unsigned 32-bit integers
		* Each key-value pair needs to begin with the number of bytes, as an unsigned 8-bit integer, the size of the
	* After the header, the bytes representing the image as RGB values are written, matching the dimensions indicated by the width/height values
	* The file ends with EOF byte
	* The program cannot make use of any libraries outside what is available on our linux distro, and cannot use any image processing libraries.
	* Source code must be written in C/C++

- [ ] Create a very simple RGB file to use for testing. Consider using a hex editor
- [ ] Create simple Makefile that creates the executable
- [ ] Implement it
