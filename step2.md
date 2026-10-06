Now, let's create a Python script to extract a specific page range (representing a chapter or module) from a source PDF.

1. Create a python file named `extract.py`:

```bash
cat << 'EOF' > extract.py
from pypdf import PdfReader, PdfWriter

# For demonstration, ensure you point this to a valid PDF file.
# If you don't have one, you can download a sample PDF.
import urllib.request
urllib.request.urlretrieve("[https://www.w3.org/W3C/About/TheW3Cbrochure.pdf](https://www.w3.org/W3C/About/TheW3Cbrochure.pdf)", "sample.pdf")

reader = PdfReader("sample.pdf")
writer = PdfWriter()

# Extract pages 2 through 4 (Python uses 0-based indexing: index 1 to 4)
start_page = 1
end_page = 4

for page_num in range(start_page, end_page):
    writer.add_page(reader.pages[page_num])

with open("extracted_module.pdf", "wb") as f:
    writer.write(f)

print("Module successfully extracted to extracted_module.pdf!")
EOF
```{{exec}}

2. Run the script:

```bash
python3 extract.py
```{{exec}}

You can verify that the new file `extracted_module.pdf` was successfully created by checking your directory:

```bash
ls -lh extracted_module.pdf
```{{exec}}
