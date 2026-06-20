# PDF to Word Converter - محول PDF إلى وورد

تطبيق Python لتحويل ملفات PDF إلى مستندات Word (.docx) مع دعم OCR لاستخراج النصوص من الصور بدقة عالية وسرعة كبيرة.

A Python application to convert PDF files to Word documents (.docx) with OCR support for extracting text from images with high accuracy and speed.

## المميزات Features

- ✅ استخراج النصوص من PDF باستخدام OCR (Extract text from PDF using OCR)
- ✅ دعم اللغتين الإنجليزية والعربية (Support for English and Arabic)
- ✅ حفظ الصور المضمنة في المستند (Save embedded images in document)
- ✅ دقة عالية 300 DPI (High accuracy 300 DPI)
- ✅ معالجة سريعة للصفحات (Fast page processing)
- ✅ واجهة سطر أوامر بسيطة (Simple command-line interface)

## المتطلبات Requirements

### تثبيت المتطلبات النظامية Install System Requirements

**على Ubuntu/Debian:**
```bash
sudo apt-get update
sudo apt-get install -y tesseract-ocr poppler-utils
```

**على macOS:**
```bash
brew install tesseract poppler
```

### تثبيت مكتبات Python Install Python Libraries

```bash
pip install pdf2image pytesseract python-docx Pillow
```

## طريقة الاستخدام Usage

### الاستخدام الأساسي Basic Usage
```bash
python pdf_to_word.py input.pdf
```
سيتم إنشاء ملف `input.docx` في نفس المجلد / File `input.docx` will be created in the same folder.

### تحديد اسم الملف الناتج Specify Output Filename
```bash
python pdf_to_word.py input.pdf output.docx
```

### مثال Example
```bash
# تحويل ملف PDF إلى Word
python pdf_to_word.py document.pdf

# تحويل مع تحديد اسم الملف الناتج
python pdf_to_word.py document.pdf my_document.docx
```

## استخدام الكود كـ Module Using as Module

```python
from pdf_to_word import convert_pdf_to_word

# تحويل بسيط Simple conversion
output_path = convert_pdf_to_word('input.pdf')

# تحويل مع تحديد مسار الإخراج Conversion with output path
output_path = convert_pdf_to_word('input.pdf', 'output.docx')
```

## البنية التقنية Technical Architecture

### كيفية العمل How It Works:
1. **تحويل PDF إلى صور**: يتم تحويل كل صفحة إلى صورة بدقة 300 DPI
   Convert PDF to Images: Each page is converted to an image at 300 DPI
2. **استخراج النصوص**: استخدام Tesseract OCR لقراءة النصوص من الصور
   Extract Text: Use Tesseract OCR to read text from images
3. **إنشاء Word**: إضافة النصوص والصور إلى مستند Word
   Create Word: Add text and images to Word document
4. **الحفظ**: حفظ الملف النهائي بصيغة .docx
   Save: Save final file as .docx

### اللغات المدعومة Supported Languages:
- الإنجليزية English
- العربية Arabic

## الأداء Performance

- **السرعة Speed**: حوالي 2-5 ثواني لكل صفحة (يعتمد على التعقيد) / About 2-5 seconds per page (depends on complexity)
- **الدقة Accuracy**: 90-95% للنصوص الواضحة / 90-95% for clear text
- **حجم الملفات File Size**: الملفات الناتجة تحتوي على نصوص وصور / Output files contain text and images

## استكشاف الأخطاء Troubleshooting

### خطأ "poppler not found"
```bash
# Ubuntu/Debian
sudo apt-get install poppler-utils

# macOS
brew install poppler
```

### خطأ "tesseract not found"
```bash
# Ubuntu/Debian
sudo apt-get install tesseract-ocr

# macOS
brew install tesseract
```

### مشاكل مع النصوص العربية Issues with Arabic Text
```bash
# تثبيت اللغة العربية Install Arabic language
sudo apt-get install tesseract-ocr-ara
```

## الترخيص License
MIT License - استخدام حر Free to use
