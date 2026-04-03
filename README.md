# WhatsApp Chat Analyzer

A Streamlit-based web application that analyzes WhatsApp chat exports to provide insights and statistics about conversations.

## 📋 Table of Contents
- [Features](#features)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Requirements](#requirements)

---

## ✨ Features

- **Message Statistics**: View total messages, words, media files, and links shared
- **Monthly Timeline**: Visualize message trends over time
- **User Analysis**: Analyze individual users or overall group statistics
- **Word Cloud**: Generate word clouds for message content
- **User Rankings**: Identify most active users
- **Emoji Analysis**: Track emoji usage patterns
- **URL Extraction**: Identify and count shared links

---

## 🚀 Installation

Follow these steps to set up the project:

### Step 1: Clone or Download the Repository
```bash
# Navigate to your desired directory
cd /path/to/project
```

### Step 2: Create a Virtual Environment (Optional but Recommended)
```bash
# Using conda (if installed)
conda create -n whatsapp-analyzer python=3.10
conda activate whatsapp-analyzer

# OR using venv
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### Step 3: Install Required Dependencies
```bash
pip install -r requirements.txt
```

The following packages will be installed:
- `streamlit` - Web app framework
- `matplotlib` - Plotting library
- `seaborn` - Data visualization
- `urlextract` - Extract URLs from text
- `wordcloud` - Generate word clouds
- `pandas` - Data manipulation
- `emoji` - Emoji handling

---

## 📁 Project Structure

```
whatsapp/
├── app.py                 # Main Streamlit application
├── preprocessor.py        # Data preprocessing module
├── helper.py             # Analysis helper functions
├── requirements.txt      # Python dependencies
├── stop_hinglish.txt     # Stop words for Hindi-English mix
└── README.md            # This file
```

### File Descriptions:

**app.py** - Main application file
- Creates the Streamlit UI with sidebar
- Handles file upload
- Displays statistics and visualizations

**preprocessor.py** - Data preprocessing
- Parses WhatsApp chat export format
- Extracts timestamps, users, and messages
- Generates temporal features (date, hour, day, etc.)

**helper.py** - Analysis functions
- Statistical calculations
- Word cloud generation
- Most active users analysis
- Emoji sentiment analysis

**stop_hinglish.txt** - Language filter
- Contains common stop words in Hindi-English mix
- Used to improve word cloud quality

---

## 📖 Usage

### Step 1: Export Your WhatsApp Chat
1. Open WhatsApp on your mobile phone
2. Select the chat you want to analyze
3. Tap Options → More → Export chat
4. Choose "Without Media" option
5. Save the exported `.txt` file

### Step 2: Run the Application
```bash
streamlit run app.py
```

This will open a local web server at `http://localhost:8501`

### Step 3: Upload and Analyze
1. Click the **"Choose a file"** button in the sidebar
2. Select your exported WhatsApp chat file (`.txt`)
3. The file will be automatically preprocessed
4. Select a user from the dropdown or choose **"Overall"** for group statistics
5. Click **"Show Analysis"** to see the results

### Step 4: View Results
The application displays:
- **Top Statistics**: Total messages, words, media, and links
- **Monthly Timeline**: Graph showing message frequency over time
- **Other Analytics**: Additional insights (expandable features)

---

## 🔍 How It Works

### Data Flow:

1. **File Upload** → User uploads WhatsApp chat export
2. **Preprocessing** → Chat data is parsed and formatted into a DataFrame
3. **Filtering** → Data is filtered by selected user or shown overall
4. **Analysis** → Statistics are calculated using helper functions
5. **Visualization** → Results are displayed with charts and graphs

### Key Functions:

**preprocess()** - Converts raw chat text to structured DataFrame
- Uses regex to extract timestamps and messages
- Splits messages into user and content
- Generates time-based features

**fetch_stats()** - Calculates core statistics
- Message count
- Word count
- Media count
- Link count

**monthly_timeline()** - Creates time-series data
- Aggregates messages by month
- Used for trend visualization

---

## 📦 Requirements

- Python 3.8+
- All dependencies listed in `requirements.txt`
- WhatsApp chat export file (`.txt` format)

For specific versions, see `requirements.txt`

---

## 🎯 Tips for Best Results

1. **Chat Export**: Use "Without Media" option to reduce file size
2. **User Selection**: Choose "Overall" to see group-wide patterns
3. **Stop Words**: The `stop_hinglish.txt` file filters common words for clearer insights
4. **Privacy**: Exported chats don't include media files (as per export option)

---

## 🐛 Troubleshooting

**Issue**: "No such file or directory: 'stop_hinglish.txt'"
- **Solution**: Ensure `stop_hinglish.txt` is in the same directory as the other Python files

**Issue**: App crashes on file upload
- **Solution**: Ensure your chat export is in the correct WhatsApp format (export from the app, not manual copy)

**Issue**: No data appears after analysis
- **Solution**: Verify the selected user exists in the chat or select "Overall"

---

## 📝 License

This project is open source and available for educational purposes.

---

## 🤝 Contributing

Feel free to fork, modify, and enhance this project. Suggestions for improvements:
- Add real-time chat statistics
- Implement sentiment analysis
- Add emoji sentiment tracking
- Create downloadable reports

---

**Last Updated**: April 2026
