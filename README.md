# PDF to Word Converter for Bangla Text

This Python-based tool converts PDF documents containing Bangla (Bengali) and English text into editable Word documents. The application uses advanced OCR (Optical Character Recognition) techniques to extract text from image-based PDFs with support for multi-language content.

## Features

- **Multi-language OCR Support**: Processes both Bangla (Bengali) and English text within the same document
- **Smart Language Detection**: Automatically determines the best OCR approach for each page
- **Advanced Image Processing**: Improves text recognition through preprocessing techniques
- **Error Handling**: Implements fallback mechanisms when primary OCR methods fail
- **Automatic Document Formatting**: Organizes extracted text into a structured Word document
- **Temporary File Management**: Cleans up all temporary files after processing

## Uniqueness

- **Combined Language Processing**: Uses `ben+eng` for dual-language recognition, outperforming single-language approaches
- **Adaptive OCR Strategy**: Analyzes OCR results and switches between different language models based on content quality
- **Image Enhancement Pipeline**: Applies grayscale conversion, Gaussian blur, and Otsu thresholding to optimize text detection
- **Failsafe File Saving**: Implements multiple save locations and unique filenames to prevent data loss
- **Minimal Dependencies**: Uses widely available Python libraries for maximum compatibility

## Requirements

- Python 3.x
- Tesseract OCR with Bengali language data
- Required Python packages:
  - pytesseract
  - pdf2image
  - opencv-python (cv2)
  - python-docx
  - pillow (PIL)
  - numpy

## Installation

1. Install Tesseract OCR with Bengali language support:
   ```
   # For Windows: Download from https://github.com/UB-Mannheim/tesseract/wiki
   # Select Bengali during installation
   ```

2. Install required Python packages:
   ```
   pip install pytesseract pdf2image opencv-python python-docx pillow numpy
   ```

3. For pdf2image, install Poppler:
   ```
   # For Windows: Download from https://github.com/oschwartz10612/poppler-windows/releases/
   # Add the bin directory to your PATH
   ```

## Usage

1. Place your PDF file in the project directory
2. Update the script with your PDF filename:
   ```python
   process_pdf("your_bangla_document.pdf", "output_document.docx")
   ```
3. Run the script:
   ```
   python app.py
   ```
4. The converted Word document will be saved in the project directory or on your Desktop

## How It Works

1. **PDF to Images**: Converts each page of the PDF to high-quality images
2. **Image Preprocessing**: Enhances image quality for better text recognition
3. **Multi-stage OCR**:
   - Attempts combined Bengali+English recognition
   - Falls back to individual language processing if needed
   - Selects the best result based on content quality
4. **Document Generation**: Compiles all extracted text into a structured Word document
5. **Cleanup**: Removes all temporary files and images

## Troubleshooting

- If you encounter "Tesseract not found" errors, ensure Tesseract is installed and the path is correctly set in the script
- For "Language data not found" errors, verify that Bengali language files are properly installed
- If permission errors occur when saving, the script will automatically attempt to save to your Desktop

## Future Enhancements

- Add support for additional Indian languages
- Implement layout preservation for complex documents
- Create a user-friendly GUI interface
- Add batch processing for multiple documents
- Incorporate formatting retention (bold, italic, etc.)
