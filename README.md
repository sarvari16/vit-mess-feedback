VIT Mess Suggestions

📌 Project Overview
VIT Mess Suggestion is a feedback collection system designed for VIT students to submit their mess-related feedback easily. The website allows students to provide feedback on food quality, quantity, hygiene, mess timings, and more. Additionally, they can upload supporting files (JPG, PNG, PDF) and track their submissions.
🎯 Features
- 📝 Feedback Form : Students can submit their feedback along with attachments.
- 📊 Category-Based Feedback: Quality, Quantity, Hygiene, Mess Timing, and Others.
- 📅 Mess Timings Display: Shows the standard mess schedule.
- 📜 Mess Rules & Regulations: Displays mess guidelines.
- 📂 File Upload Support: Accepts image and PDF files.
- 📡 Google Apps Script Backend: Stores data in a Google Sheet & uploads files to Google Drive.
- 📱 Responsive Design: Works on mobile, tablet, and desktop.

🏗️ Technologies Used
- Frontend: HTML, CSS, JavaScript
- Backend: Google Apps Script
- Database: Google Sheets
- File Storage: Google Drive
- Icons & Fonts: Font Awesome, Google Fonts (Poppins)

 🛠️ Setup Instructions
1️⃣ Deploying the Website
1. Clone this repository:
   Editing vit-mess-feedback/README.md at main · sarvari16/vit-mess-feedback
2. Open `index.html` in your browser to test the UI.

2️⃣ Setting Up Google Apps Script Backend
1. Open [Google Sheets](https://docs.google.com/spreadsheets/).
2. Create a new sheet & copy its **Spreadsheet ID** (from the URL).
3. Open [Google Apps Script](https://script.google.com/).
4. Copy the `appscript.gs` code & paste it into the editor.
5. Replace the `Spreadsheet ID` and `Google Drive Folder ID`.
6. Deploy as a Web App (`Anyone can access` permission).
7. Copy the **Deployment URL** and update it in `index.html`.

🚀 Deploying on GitHub Pages
You can host your website for free using **GitHub Pages**:
1. Push the code to GitHub.
2. Go to **Settings > Pages**.
3. Select the branch (`main` or `master`).
4. Click **Save**, and your website will be live!

 📂 Project Structure
📁 vit-mess-feedback/
├── 📄 index.html  # Main HTML file
├── 🎨 styles.css  # Stylesheet
├── 📜 appscript.gs # Google Apps Script backend
└── 📄 README.md   # Project documentation
```

 🤝 Contributors
Sathvik Mendu-23BCI0232
Siva Charan Reddy-23BDS0156
Chitimalla Sarvari - 23BCT0048

💡 _"Help us improve your mess experience by sharing your feedback!"_
