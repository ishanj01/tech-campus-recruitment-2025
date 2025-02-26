# Source Directory
import sys


  
    import sys 
    def extract_logs(log_file, date):
     output_file = f"output/output_{date}.txt"

     try:
        with open(log_file, 'r', encoding='utf-8') as infile, open(output_file, 'w', encoding='utf-8') as outfile:
            for line in infile:
                if line.startswith(date):  # Check if the line starts with the given date
                    outfile.write(line)

        print(f"Logs for {date} extracted successfully to {output_file}")

    except FileNotFoundError:
        print(f"Error: Log file '{log_file}' not found.")
    except Exception as e:
        print(f"An error occurred: {e}")

# Command-line execution
    if __name__ == "__main__":
      if len(sys.argv) != 3:
         print("Usage: python extract_logs.py <log_file_path> <YYYY-MM-DD>")
      else:
         log_file_path = sys.argv[1]
         date_str = sys.argv[2]
         extract_logs(log_file_path, date_str)
