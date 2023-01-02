The types of activities that you can perform on the opened file are controlled by Access Modes. These describe how the file will be used after it has been opened.
These modes also specify where the file handle should be located within the file. Similar to a pointer, a file handle indicates where data should be read or put into the file.

In Python, there are six methods or access modes:
1. Read Only ('r'): this mode opens the text files for reading only. The start of the file is where the handle is located. This is the default mode for opening files as well.
2. Read and Write ('r+'): this method opens the file for both reading and writing. The start of the file is where the handle is located.
3. Write only ('w'): this mode opens the file for writing only. The data in existing files are modified and overwritten. The start of the file is where the handle is located. If the file does not already exist in the folder, a new one gets created.
4. Write and Read ('w+'): this mode opens the file for both reading and writing. The text is overwritten and deleted from an existing file.
5. Append only ('a'): this mode allows the file to be opened for writing. If the file doesn't yet exist, a new one gets created. The handle is set at the end of the file. The newly written data will be added at the end, following the previously written data.
6. Append and Read ('a+'): using this method, you can read and write in the file. If the file doesn't already exist, one gets created. The handle is set at the end of the file. The newly written text will be added at the end, following the previously written data.

