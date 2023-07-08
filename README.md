# Message_logging

The Logger class, through which all work with the log file passes. Saving messages to a file on disk (log.txt). 
When a logger object is created, the file is opened, and when it is destroyed, the file is closed (RAII concept).

The class implements the following methods:

- writeLog method writing a string of logs to a file (messages from the messages vector);
- readLog method reading string with a specific number from file;
- output to console the lines written to the file (writer method) and lines read from the file (reader method).

Writing and reading are thread-safe through the use of std::shared_mutex and std::mutex - when several threads are called simultaneously to write to and read from a file, no interlocking and data races occur.
