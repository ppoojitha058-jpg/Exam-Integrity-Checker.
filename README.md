# 📚 Smart Learning App - AI-Powered Exam Generator

A beautiful, full-featured web application that transforms your study materials into interactive exams with intelligent question generation, text-to-speech, real-time scoring, and detailed analytics.

## ✨ Features

### 🎯 Core Features
- **Smart Question Generation**: AI-powered generation of MCQs and descriptive questions with varying difficulty levels (Easy, Medium, Hard)
- **Multiple Input Methods**: 
  - Paste text directly
  - Upload PDF documents
  - Upload Word documents (DOC/DOCX)
  - Upload images (PNG/JPG/JPEG) with OCR support
- **Timed Exam Mode**: 30-minute countdown timer with visual warnings and auto-submit
- **Text-to-Speech**: Read questions aloud using browser's speech synthesis
- **Progress Tracking**: Real-time progress bar showing answered/unanswered questions
- **Smart Validation**: Highlight unanswered questions before submission
- **Auto-Save**: Progress automatically saved every 30 seconds
- **Keyboard Shortcuts**: Ctrl+S to save, Ctrl+Enter to submit

### 📊 Scoring & Analytics
- **Intelligent Scoring**:
  - MCQ: 2 points each with auto-grading
  - Descriptive: 3 points each with keyword matching
  - Difficulty multipliers for harder questions
- **Detailed Results**: 
  - Overall score percentage with visual circle graph
  - MCQ accuracy breakdown
  - Descriptive answer evaluation with keyword highlighting
  - Question-by-question review showing correct/incorrect answers
- **Performance Levels**: Excellent (80%+), Good (60%+), Average (<60%)

### 📄 PDF Export
- Download beautiful PDF reports containing:
  - Student information and timestamp
  - Complete score breakdown
  - All questions with difficulty levels
  - Your answers vs correct answers
  - Color-coded results (green for correct, red for incorrect)

### 📈 History & Tracking
- View all previous attempts
- Statistics dashboard showing:
  - Total attempts
  - Average score
  - Number of excellent scores
- Individual attempt details with download option

### 🎨 Beautiful UI/UX
- Modern, gradient-based design
- Smooth animations and transitions
- Responsive layout for all devices
- Card-based question display with hover effects
- Color-coded difficulty badges
- Interactive form elements
- Professional color scheme

## 🚀 Quick Start

### Prerequisites
- Python 3.12 (or Python 3.8+)
- pip (Python package manager)
- (Optional) Tesseract OCR for image text extraction

### Installation

1. **Clone or navigate to the project directory**
```bash
cd c:\Users\Prathibha\Desktop\e
```

2. **Create a virtual environment**
```bash
python -m venv venv
```

3. **Activate the virtual environment**
- Windows:
```bash
venv\Scripts\activate
```
- macOS/Linux:
```bash
source venv/bin/activate
```

4. **Install required packages**
```bash
pip install -r requirements.txt
```

5. **Install Tesseract (Optional - for OCR from images)**
- Windows: Download and install from https://github.com/UB-Mannheim/tesseract/wiki
- macOS: `brew install tesseract`
- Linux: `sudo apt-get install tesseract-ocr`

### Running the Application

1. **Start the Flask server**
```bash
python app.py
```

2. **Open your browser**
Navigate to: `http://127.0.0.1:5000/`

3. **Start learning!** 🎉

## 📖 How to Use

### Step 1: Upload Content
1. Enter your name
2. Choose input method:
   - **Paste Text**: Copy and paste your lesson content
   - **Upload File**: Select a PDF, DOC, DOCX, or image file
3. Click "Generate Smart Exam"

### Step 2: Take the Exam
- **Timer**: 30 minutes countdown with color warnings
- **Progress Bar**: Track answered vs unanswered questions
- **Read Aloud**: Click to hear all questions
- **Highlight Unanswered**: See which questions need attention
- **Next Question**: Jump to next unanswered question
- Answer all questions (MCQs + Descriptive)
- Click "Submit Exam"

### Step 3: View Results
- See your score percentage with animated circle graph
- Review detailed breakdown:
  - MCQ correct/incorrect with correct answers shown
  - Descriptive answers with keyword analysis
- Download PDF report
- View all previous attempts

### Step 4: Track Progress
- Click "View Previous Attempts" from home page
- See statistics dashboard
- Review individual attempts
- Download any previous result as PDF

## 🎮 Keyboard Shortcuts
- `Ctrl+S` or `Cmd+S`: Save progress
- `Ctrl+Enter` or `Cmd+Enter`: Submit exam (with confirmation)

## 🎯 Question Types

### Multiple Choice Questions (MCQs)
- **Easy**: Direct fact-based questions
- **Medium**: Conceptual understanding
- **Hard**: Application and analysis
- 4 options per question
- Auto-graded with instant feedback

### Descriptive Questions
- **Easy**: Summary and main ideas
- **Medium**: Explanation with examples
- **Hard**: Real-world application and detailed analysis
- Keyword-based scoring
- Partial credit for matching keywords

## 📁 Project Structure
```
e/
├── app.py                 # Flask backend with all routes
├── requirements.txt       # Python dependencies
├── README.md             # This file
├── templates/
│   ├── index.html        # Landing page with upload/paste
│   ├── exam.html         # Exam page with timer and questions
│   ├── result.html       # Individual result with detailed breakdown
│   └── results_list.html # All attempts history
├── static/
│   ├── style.css         # Beautiful modern styling
│   └── main.js           # Timer, TTS, validation, auto-save
├── uploads/              # Temporary file storage
└── attempts/             # JSON files with exam results
```

## 🛠️ Technical Stack

### Backend
- **Flask 3.0**: Web framework
- **PyPDF2**: PDF text extraction
- **python-docx**: Word document processing
- **Pillow + Pytesseract**: Image OCR
- **FPDF**: PDF generation

### Frontend
- **HTML5**: Semantic markup
- **CSS3**: Modern styling with gradients, animations
- **JavaScript**: Interactive features, SpeechSynthesis API
- **No external CSS/JS frameworks**: Pure, lightweight code

### Features Implementation
- **Smart Question Generation**: Text analysis with regex and randomization
- **Timer**: JavaScript setInterval with visual feedback
- **Text-to-Speech**: Browser's SpeechSynthesis API
- **Progress Tracking**: Real-time DOM updates
- **Auto-Save**: localStorage with 30s intervals
- **PDF Generation**: FPDF with colored, formatted output

## 🎨 Design Philosophy
- **Modern & Clean**: Gradient backgrounds, card-based layout
- **User-Friendly**: Clear labels, helpful hints, visual feedback
- **Accessible**: Keyboard shortcuts, text-to-speech support
- **Responsive**: Works on desktop, tablet, and mobile
- **Professional**: Color-coded results, structured reports

## 🔧 Configuration

### Timer Duration
Change in `exam.html` line where `startTimer` is called:
```javascript
startTimer(30, "time", "examForm"); // 30 minutes
```

### Question Count
Modify in `app.py` in the `generate_questions` function:
```python
return mcqs[:6], descriptive[:3]  # 6 MCQs, 3 descriptive
```

### Scoring Weights
Adjust in `app.py` in the `calculate_score` function:
```python
mcq_score += 2  # Points per MCQ
points = (match_count / len(keywords)) * 3  # Points per descriptive
```

## 🐛 Troubleshooting

### ImportError: No module named 'flask'
```bash
pip install -r requirements.txt
```

### Tesseract not found error
Install Tesseract OCR and add to PATH, or disable image upload

### Timer not working
Ensure JavaScript is enabled in your browser

### PDF download not working
Check that FPDF is installed: `pip install fpdf`

## 🚀 Future Enhancements
- [ ] AI-powered descriptive answer evaluation using NLP
- [ ] Difficulty level selection by user
- [ ] Custom timer duration
- [ ] Multiple exam sessions
- [ ] Export results to Excel
- [ ] Question bank management
- [ ] Admin dashboard
- [ ] User authentication
- [ ] Leaderboard
- [ ] Practice mode without timer

## 📝 License
This project is open source and available for educational purposes.

## 👨‍💻 Developer Notes
- Uses Python 3.12 features but compatible with 3.8+
- No database required - uses JSON file storage
- Pure Flask - no SQLAlchemy or ORM
- Lightweight and fast
- Easy to deploy

## 🎓 Perfect For
- Students preparing for exams
- Teachers creating quick assessments
- Self-learners testing knowledge
- Study groups
- Online tutoring
- Educational institutions

## 📞 Support
For issues or questions, check the code comments or create an issue.

---

Made with ❤️ for better learning experiences!
