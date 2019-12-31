# file-sort

This program uses a polyphase mergesort algorithm to sort a csv text file. Written in C++ by Daniel Rencricca.

Each line of text in the file must be a distinct record that ends with	an endline ('\n') character. Additionally, each record must contains fields separated by commas or tabs, where one of these fields will be used as a sort key to sort the records in the file. It does the sort by performing the following steps: (1) create a total of MAX_SRT_FILES sort files to be used to temporarily hold record data; (2) read up to MAX_ARR_SZ records (i.e. lines of text) into a buffer array, where each element of the array consists of the record (i.e. a line of text)  and the sort key that is copied from that record; (3) sort the array by the key; (4) find the lowest key in the buffer that is greater than the last key read, and copy the record associated with that key from the buffer to a temporary sort file; (5) read in one new record (i.e. line of text) and add it to its correct sorted postion; (7) repeat from step 3 until there are no more keys left that are greater than the last key read; (8) repeat from step 2 until the last sort file has been filled; (9) read the first record from each of the sort files into a tempfile array and get the sort key from each record; (10) Find the lowest key in the tempfile array and write the associated record into a temporary holder file;	(11) read a new text string from the sort file which previously had the lowest key and get the key from that string; (12) repeat from	step 10 until all sort files have been fully read; (13) erase the sort files and repeat from step 1 until the input file has been fully read.
