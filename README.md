# File Reader Example in Go

This project provides a simple example of reading and printing a file from disk using Go. The program takes a file path as an argument, opens the file, and prints its contents to the standard output.

## Overview

The program performs the following steps:
1. Takes a file path as a command-line argument.
2. Opens the specified file.
3. Reads the file's content and prints it to the standard output.

## Usage

To run the program, ensure you have Go installed on your system. Then, follow these steps:

1. Save the code to a file, for example, `main.go`.
2. Open a terminal and navigate to the directory containing `main.go`.
3. Run the following command to execute the program, passing the file path as an argument:

```bash
go run main.go <file_path>
```

Replace `<file_path>` with the path to the file you want to read. For example:

```bash
go run main.go example.txt
```

## Code Explanation

The main components of the code are:

1. **Opening the File:**
   ```go
   f, err := os.Open(os.Args[1])
   if err != nil {
       fmt.Println("Error: ", err)
       os.Exit(1)
   }
   ```

   The program takes the file path from the command-line arguments and attempts to open the file. If there is an error (e.g., the file does not exist), it prints an error message and exits the program.

2. **Reading and Printing the File Content:**
   ```go
   io.Copy(os.Stdout, f)
   ```

   The `io.Copy` function is used to copy the contents of the file to the standard output (i.e., the terminal). This effectively prints the file's contents to the terminal.

## Notes

- Ensure that the file path provided as an argument is correct and that the file is accessible.
- If you encounter any errors (e.g., file not found), the program will print an error message and exit with a non-zero status code.

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue if you have any suggestions or improvements.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
