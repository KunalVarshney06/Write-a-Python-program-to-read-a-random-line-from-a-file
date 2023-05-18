# Write-a-Python-program-to-read-a-random-line-from-a-file
import random
import linecache

def read_random_line(file_path):
    try:
        line_count = sum(1 for _ in open(file_path))
        random_line_number = random.randint(1, line_count)
        random_line = linecache.getline(file_path, random_line_number).strip()
        return random_line
    except FileNotFoundError:
        print("File not found.")
    except IOError:
        print("An error occurred while reading the file.")

# Example usage
file_path = 'path/to/your/file.txt'  # Replace with the actual file path
random_line = read_random_line(file_path)
if random_line:
    print("Random line:", random_line)
