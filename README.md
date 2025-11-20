# 📊 Data Explorer - CSV Analysis Dashboard

<div align="center">

![GitHub](https://img.shields.io/github/license/ShreyashPatil530/A-full-stack-MERN-application-for-Data-Explorer---CSV-Analysis-Dashboard?style=flat-square)
![GitHub Stars](https://img.shields.io/github/stars/ShreyashPatil530/A-full-stack-MERN-application-for-Data-Explorer---CSV-Analysis-Dashboard?style=flat-square)
![GitHub Forks](https://img.shields.io/github/forks/ShreyashPatil530/A-full-stack-MERN-application-for-Data-Explorer---CSV-Analysis-Dashboard?style=flat-square)
![Node.js Version](https://img.shields.io/badge/Node.js-v16+-green?style=flat-square)
![React Version](https://img.shields.io/badge/React-18.0+-blue?style=flat-square)
![TypeScript](https://img.shields.io/badge/TypeScript-5.2+-3178C6?style=flat-square)

**A powerful full-stack MERN application for instant CSV data analysis with real-time visualizations and advanced statistics.**

[Live Demo](#) • [Report Bug](https://github.com/ShreyashPatil530/A-full-stack-MERN-application-for-Data-Explorer---CSV-Analysis-Dashboard/issues) • [Request Feature](https://github.com/ShreyashPatil530/A-full-stack-MERN-application-for-Data-Explorer---CSV-Analysis-Dashboard/issues)

</div>

---

## ✨ Features

### 📤 **File Upload & Processing**
- Drag-and-drop CSV file upload
- Real-time file validation
- Automatic file type detection
- Support for large datasets (up to 50MB)

### 📊 **Data Analysis**
- Automatic column type detection (numeric, categorical, date, boolean)
- Real-time statistical calculations
- Missing value & duplicate row detection
- Advanced outlier detection using IQR method
- Data completeness scoring

### 📈 **Interactive Visualizations**
- Histograms for numeric distributions
- Pie charts for categorical data
- Bar charts for frequency analysis
- Real-time chart updates
- Responsive design for all devices

### 🔢 **Advanced Statistics**
- Mean, Median, Standard Deviation
- Min, Max, Quartiles (Q1, Q3)
- Interquartile Range (IQR)
- Outlier detection & counting
- Distribution analysis

### 💾 **Data Management**
- MongoDB integration for data persistence
- Analysis history tracking
- Auto-delete records after 30 days
- RESTful API architecture
- Secure data handling

### 🎨 **Modern UI/UX**
- Responsive design with Tailwind CSS
- Beautiful gradient backgrounds
- Smooth animations & transitions
- Intuitive component layout
- Dark mode ready

---

## 🛠️ Tech Stack

### **Frontend** 🎨
```
├── React 18.2.0 (UI Library)
├── TypeScript 5.2.2 (Type Safety)
├── Tailwind CSS 3.3.6 (Styling)
├── Recharts 2.10.0 (Visualizations)
├── Axios 1.6.0 (API Client)
├── Lucide React (Icons)
└── React Icons (Additional Icons)
```

### **Backend** ⚙️
```
├── Node.js + Express (Server)
├── TypeScript 5.2.2 (Type Safety)
├── MongoDB + Mongoose (Database)
├── Multer (File Upload)
├── csv-parser (CSV Parsing)
└── CORS (Cross-origin Support)
```

### **Database** 💾
```
└── MongoDB Atlas (Cloud Database)
    ├── Analysis History Collection
    ├── Automatic TTL Indexes
    └── Real-time Timestamps
```

---

## 🚀 Quick Start

### Prerequisites
- **Node.js** v16+ ([Download](https://nodejs.org/))
- **npm** v7+ 
- **MongoDB Atlas** account ([Sign up](https://www.mongodb.com/cloud/atlas))
- **Git** installed

### Installation

#### 1️⃣ Clone the Repository
```bash
git clone https://github.com/ShreyashPatil530/A-full-stack-MERN-application-for-Data-Explorer---CSV-Analysis-Dashboard.git
cd A-full-stack-MERN-application-for-Data-Explorer---CSV-Analysis-Dashboard
```

#### 2️⃣ Backend Setup
```bash
cd server

# Install dependencies
npm install

# Create .env file
echo PORT=5000 > .env
echo NODE_ENV=development >> .env
echo CLIENT_URL=http://localhost:3000 >> .env
echo MONGODB_URI=your_mongodb_uri_here >> .env
echo DB_NAME=data_explorer >> .env
echo MAX_FILE_SIZE=52428800 >> .env

# Start development server
npm run dev
```

#### 3️⃣ Frontend Setup
```bash
cd ../client

# Install dependencies
npm install --legacy-peer-deps

# Create .env file
echo REACT_APP_API_URL=http://localhost:5000/api > .env

# Start development server
npm start
```

#### 4️⃣ Access the Application
Open your browser and navigate to:
```
http://localhost:3000
```

---

## 📖 Usage Guide

### Step 1: Upload CSV File
1. Click **"Browse Files"** or drag-drop a CSV file
2. File is validated automatically
3. Click **"Upload & Analyze"**

### Step 2: View Analysis Results
- **KPI Cards**: 8 key metrics
- **Data Preview**: First 10 rows
- **Charts**: Interactive visualizations
- **Statistics**: Detailed numerical analysis

### Step 3: Explore Data
- Switch between numeric/categorical columns
- View distribution charts
- Check statistical summaries
- Download analysis report

---

## 🔌 API Endpoints

### Upload & Analyze CSV
```bash
POST /api/upload
Content-Type: multipart/form-data

Body: CSV file
Response: Analysis result JSON
```

### Get Analysis History
```bash
GET /api/history?limit=10&skip=0

Response: {
  "success": true,
  "data": [...],
  "total": 50,
  "limit": 10,
  "skip": 0
}
```

### Get Specific Analysis
```bash
GET /api/history/:id

Response: {
  "success": true,
  "data": { analysis object }
}
```

### Delete Analysis
```bash
DELETE /api/history/:id

Response: {
  "success": true,
  "message": "Analysis deleted successfully"
}
```

### Health Check
```bash
GET /health

Response: {
  "status": "Backend is running",
  "timestamp": "2024-01-15T10:30:00.000Z",
  "database": "connected"
}
```

---

## 📁 Project Structure

```
data-explorer/
├── 📂 server/
│   ├── src/
│   │   ├── config/
│   │   │   └── database.ts         # MongoDB connection
│   │   ├── controllers/
│   │   │   └── uploadController.ts # File upload logic
│   │   ├── models/
│   │   │   └── AnalysisHistory.ts  # MongoDB schema
│   │   ├── routes/
│   │   │   ├── uploadRoutes.ts
│   │   │   └── historyRoutes.ts
│   │   ├── utils/
│   │   │   ├── csvParser.ts        # CSV parsing
│   │   │   ├── dataAnalysis.ts     # Statistical calculations
│   │   │   └── typeDetection.ts    # Column type detection
│   │   ├── types/
│   │   │   └── index.ts            # TypeScript interfaces
│   │   ├── middleware/
│   │   │   └── errorHandler.ts
│   │   └── index.ts                # Server entry point
│   ├── .env                        # Environment variables
│   ├── package.json
│   └── tsconfig.json
│
├── 📂 client/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── Dashboard.tsx       # Main dashboard
│   │   │   ├── FileUpload.tsx      # Upload component
│   │   │   ├── KPICard.tsx         # KPI display
│   │   │   ├── DataPreview.tsx     # Data table
│   │   │   └── Charts.tsx          # Visualizations
│   │   ├── api/
│   │   │   └── axiosConfig.ts      # API client
│   │   ├── types/
│   │   │   └── index.ts            # TypeScript types
│   │   ├── App.tsx
│   │   ├── App.css
│   │   ├── index.tsx
│   │   └── index.css               # Tailwind styles
│   ├── .env
│   ├── package.json
│   └── tsconfig.json
│
└── README.md                        # This file
```

---

## 📊 Data Analysis Features

### Column Type Detection
- **Numeric**: Integers, decimals, scientific notation
- **Categorical**: Strings, mixed data
- **Date**: ISO format, US format, custom formats
- **Boolean**: true/false, yes/no, 1/0

### Statistical Metrics
| Metric | Description |
|--------|-------------|
| **Mean** | Average value |
| **Median** | Middle value |
| **Std Dev** | Standard deviation |
| **Min/Max** | Minimum & maximum values |
| **Q1/Q3** | First & third quartiles |
| **IQR** | Interquartile range |
| **Outliers** | Values outside 1.5×IQR bounds |

### Data Quality Metrics
| Metric | Purpose |
|--------|---------|
| **Total Rows** | Number of data records |
| **Total Columns** | Number of features |
| **Missing %** | Percentage of empty cells |
| **Duplicates %** | Percentage of duplicate rows |
| **Completeness** | Quality score (100% - missing%) |
| **Numeric Cols** | Count of numeric columns |
| **Categorical Cols** | Count of text columns |

---

## 🔐 Environment Variables

### Backend (.env)
```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/?appName=Cluster0
DB_NAME=data_explorer

# Frontend
CLIENT_URL=http://localhost:3000

# File Upload
MAX_FILE_SIZE=52428800
UPLOAD_DIR=./uploads
```

### Frontend (.env)
```env
# API Configuration
REACT_APP_API_URL=http://localhost:5000/api
```

---

## 🚀 Deployment

### Deploy Frontend (Vercel)

```bash
cd client
npm run build

# Deploy to Vercel
vercel --prod
```

**Environment Variables:**
```
REACT_APP_API_URL=your_backend_url/api
```

### Deploy Backend (Render/Heroku)

```bash
cd server
npm run build

# Deploy to Render/Heroku
# Follow platform-specific instructions
```

**Environment Variables:**
```
PORT=5000
MONGODB_URI=your_mongodb_uri
DB_NAME=data_explorer
CLIENT_URL=your_frontend_url
```

---

## 🧪 Testing

### Test File Upload
```bash
curl -X POST http://localhost:5000/api/upload \
  -F "file=@sample.csv"
```

### Test API Health
```bash
curl http://localhost:5000/health
```

### Test Analysis History
```bash
curl http://localhost:5000/api/history
```

---

## 🐛 Troubleshooting

### Issue: "MongoDB connection error"
**Solution:**
- Verify MongoDB URI in `.env`
- Whitelist your IP in MongoDB Atlas
- Check database is running

### Issue: "CORS error"
**Solution:**
- Verify `CLIENT_URL` in backend `.env`
- Check frontend URL matches
- Clear browser cache

### Issue: "File upload fails"
**Solution:**
- Check file size < 50MB
- Verify CSV format
- Check `uploads/` directory exists

### Issue: "Port already in use"
**Solution:**
```bash
# For port 5000
npx kill-port 5000

# For port 3000
npx kill-port 3000
```

---

## 📈 Performance Metrics

| Metric | Value |
|--------|-------|
| **Load Time** | < 2 seconds |
| **Analysis Time** | < 5 seconds (10K rows) |
| **Max File Size** | 50 MB |
| **Supported Rows** | 100K+ |
| **Database TTL** | 30 days |

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** changes (`git commit -m 'Add AmazingFeature'`)
4. **Push** to branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Contribution Guidelines
- Follow existing code style
- Add comments for complex logic
- Update README if needed
- Test before submitting PR

---

## 📝 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **React** - UI library
- **MongoDB** - Database
- **Tailwind CSS** - Styling
- **Recharts** - Visualizations
- **TypeScript** - Type safety
- **Node.js/Express** - Backend framework

---

## 👨‍💻 Author

**Shreyash Patil**

- 🔗 GitHub: [@ShreyashPatil530](https://github.com/ShreyashPatil530)
- 📧 Email: shreyashpatil530@gmail.com
- 💼 LinkedIn: [Your LinkedIn Profile](https://www.linkedin.com/in/shreyash-patil-ba921737b/)

---

## 📞 Support

Have questions? Open an [issue](https://github.com/ShreyashPatil530/A-full-stack-MERN-application-for-Data-Explorer---CSV-Analysis-Dashboard/issues) and we'll help you out!

---

<div align="center">

### ⭐ If you find this project useful, please star it! ⭐

**Made with ❤️ using MERN Stack + TypeScript**

[⬆ back to top](#-data-explorer---csv-analysis-dashboard)

</div>
