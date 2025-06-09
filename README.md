# IyàCare - AI-Powered Maternal Healthcare Management Platform

## 🏥 Project Overview

IyàCare is a comprehensive healthcare management platform that combines machine learning models with a modern web application to provide AI-powered maternal health risk assessment and vital signs monitoring. The platform is designed to assist healthcare providers in early identification of at-risk pregnancies, particularly in low-resource settings where advanced diagnostic tools may be unavailable.

The project consists of four main components:
1. **Machine Learning Models** - XGBoost-based maternal health risk prediction models ✅
2. **Web Application** - Next.js-based healthcare management platform with real-time monitoring ✅
3. **IoT Device Integration** - Real-time monitoring from connected medical devices 🚧
4. **Blockchain Records** - Secure, immutable storage of medical records on blockchain 🚧

**Current Implementation Status:**
- ✅ **Machine Learning Models**: Fully developed and trained (85.2% accuracy)
- ✅ **Web Application**: Complete healthcare management platform with authentication, vital signs monitoring, and patient management
- 🚧 **Next Steps**: Integration of IoT devices for real-time data collection and blockchain implementation for secure medical record storage

## 🔗 GitHub Repository

**Project Repository**: [https://github.com/Tripp808/iyacare-app](https://github.com/Tripp808/iyacare-app)

## 🎥 Demo Video

**Watch the IyàCare Platform Demo**: [https://youtu.be/Kg3l-VpuHo8](https://youtu.be/Kg3l-VpuHo8)

*This demo showcases the complete functionality of the IyàCare platform, including user authentication, dashboard overview, vital signs monitoring, patient management, and AI-powered risk assessment features.*

## 🤖 AI/ML Component

### Maternal Health Risk Prediction Model

Our AI component uses machine learning to predict maternal health risks based on clinical biomarkers. The model was developed using a comprehensive data science approach with the following specifications:

#### 📊 Model Performance
- **Algorithm**: XGBoost Classifier (150 gradient-boosted trees)
- **Accuracy**: 85.2% on test set
- **ROC AUC**: 0.944
- **Cross-Validated Accuracy**: 84.0%

#### 🔬 Input Features
The model predicts risk levels using these vital signs:
- **Age** (years)
- **Systolic Blood Pressure** (mmHg) 
- **Diastolic Blood Pressure** (mmHg)
- **Blood Glucose Level** (mmol/L)
- **Body Temperature** (°F)
- **Heart Rate** (bpm)

#### 📈 Output Classifications
- **Low Risk**: Normal pregnancy progression
- **Mid Risk**: Requires monitoring and preventive care
- **High Risk**: Immediate medical intervention needed

#### 🔬 Technical Architecture
```
Model Architecture: XGBoost Classifier
├── 150 gradient-boosted decision trees
├── Maximum tree depth: 6 levels
├── Learning rate: 0.1
├── L2 regularization: λ=1
└── Early stopping after 10 non-improving rounds
```

## 🌐 Web Application

### Technology Stack

#### Frontend
- **Framework**: Next.js 15.3.2 with React 19
- **Language**: TypeScript
- **Styling**: Tailwind CSS 4.0
- **UI Components**: Radix UI, Lucide Icons
- **Charts**: Recharts for data visualization
- **Animations**: Framer Motion
- **Forms**: React Hook Form with Zod validation

#### Backend & Database
- **Authentication**: Firebase Authentication
- **Database**: Cloud Firestore
- **Security**: Firestore security rules
- **Cloud Functions**: Firebase Cloud Functions
- **File Storage**: Firebase Storage

#### Development Tools
- **Linting**: ESLint 9
- **Package Manager**: npm
- **Build Tool**: Next.js built-in bundler
- **Deployment**: Vercel (recommended)

### 🎯 Key Features

#### ✅ Authentication & User Management
- Firebase Authentication with email/password
- Email verification required for account activation
- Password reset functionality
- Role-based access control (Admin, Healthcare Provider, Healthcare Worker, Patient)
- User profile management with real-time data

#### 📊 Vital Signs Management
- Real-time vital signs recording with AI-powered risk assessment
- Historical data tracking with timestamps
- Interactive charts and visualizations
- Data validation and error handling
- Integration with ML model for automatic risk predictions

#### 👥 Patient Management
- Patient registration and profile management
- Medical history tracking
- Risk level assessment and monitoring
- Contact information management
- Healthcare provider assignment

#### 📱 Dashboard & Analytics
- Real-time statistics (Total Patients, High Risk Patients, Appointments, Alerts)
- Interactive vital signs charts with multiple metrics
- Quick access cards for common actions
- Alert notifications system
- Recent activity tracking

#### 🔐 Security Features
- Firestore security rules for data access control
- Environment variable configuration for sensitive data
- Role-based permissions for different user types
- Data encryption in transit and at rest
- GDPR compliance considerations

### 📱 Application Pages

1. **Authentication Pages**
   - `/auth/login` - User login with email verification
   - `/auth/register` - User registration with role selection
   - `/auth/forgot-password` - Password reset functionality

2. **Main Application**
   - `/dashboard` - Main dashboard with statistics and quick access
   - `/vitals` - Vital signs recording and history
   - `/patients` - Patient management and profiles
   - `/alerts` - System alerts and notifications
   - `/appointments` - Appointment scheduling and management
   - `/analytics` - Data analytics and reporting
   - `/settings` - User profile and application settings

## 🚀 Environment Setup & Installation

### Prerequisites

Before setting up the project, ensure you have:

- **Node.js** 18+ installed
- **Python** 3.8+ (for ML model development)
- **Firebase account** (free tier available)
- **Git** for version control

### 📁 Project Structure

```
iyacare_initial_product/
├── Models/                           # Trained ML models
│   ├── maternal_risk_xgboost.pkl   # XGBoost model
│   ├── maternal_risk_scaler.pkl    # Feature scaler
│   └── maternal_risk_metadata.pkl  # Model metadata
├── Notebook/                        # Data science notebooks
│   └── Oche_Ankeli_Maternal_Health_notebook.ipynb
├── UI screens                       # Application interface screenshots
├── iyacare app/                     # Web application
│   ├── src/                        # Source code
│   ├── public/                     # Static assets
│   ├── docs/                       # Documentation
│   ├── package.json               # Dependencies
│   ├── .env.example               # Environment template
│   └── README.md                  # App-specific docs
└── README.md                       # This file
```

### 🔧 Local Development Setup

#### 1. Clone the Repository

```bash
git clone https://github.com/Tripp808/iyacare-app.git
cd iyacare_initial_product
```

#### 2. Set Up the Web Application

```bash
# Navigate to the web app directory
cd "iyacare app"

# Install dependencies
npm install

# Copy environment template
cp .env.example .env.local
```

#### 3. Configure Environment Variables

Edit `.env.local` with your Firebase configuration:

```env
# Firebase Configuration
NEXT_PUBLIC_FIREBASE_API_KEY=your_firebase_api_key_here
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project_id.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id_here
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project_id.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id_here
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id_here

# AI Model Configuration (Optional)
NEXT_PUBLIC_AI_MODEL_URL=https://your-ai-model.onrender.com
NEXT_PUBLIC_AI_MODEL_API_KEY=your_ai_model_api_key_here

# Site Configuration
NEXT_PUBLIC_SITE_URL=http://localhost:3000
```

#### 4. Set Up Firebase

1. Create a Firebase project at [console.firebase.google.com](https://console.firebase.google.com)
2. Enable Authentication (Email/Password)
3. Create a Firestore database
4. Get your Firebase configuration from Project Settings
5. Deploy security rules:

```bash
# Install Firebase CLI
npm install -g firebase-tools

# Login and initialize
firebase login
firebase init

# Deploy Firestore rules
firebase deploy --only firestore:rules
```

#### 5. Run the Application

```bash
# Start development server
npm run dev

# Open your browser
# Navigate to http://localhost:3000
```

#### 6. Set Up ML Model Environment (Optional)

```bash
# Navigate back to project root
cd ..

# Create Python virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install Python dependencies
pip install scikit-learn pandas numpy xgboost joblib flask fastapi uvicorn
```

## 🎨 Design & Interface

### Application Screenshots

#### 1. Authentication System
**User Registration Page** - `/auth/register`
- Clean, professional registration form with role-based access
- Field validation and user-friendly interface
- Healthcare Provider role selection with email verification

**User Login Page** - `/auth/login`  
- Secure login with email and password
- Password reset functionality
- Terms of Service and Privacy Policy integration

#### 2. Main Dashboard - `/dashboard`
**Welcome Dashboard** - Real-time healthcare overview
- **Patient Statistics**: 11 total patients registered in the system
- **Risk Assessment Cards**: 
  - High Risk Patients: 0 (No high-risk patients)
  - Medium Risk Patients: 0 (No medium-risk patients) 
  - Unread Alerts: 0 (All clear!)
- **Quick Action Cards**:
  - Record Vital Signs - Add new readings
  - Manage Patients - View patient records
  - View Analytics - Patient insights
  - View Alerts - System notifications
- **Recent Activity Sections**:
  - Recent Vital Signs: No vital signs recorded yet
  - System Alerts: No unread alerts

#### 3. Vital Signs Monitoring - `/vitals`
**IoT Device Integration Interface**
- **Data from IoT devices** indicator showing readiness for connected medical devices
- **No Vital Signs Data** state with clear instructions
- Message: "Vital signs data will appear here automatically as IoT devices record patient measurements. Make sure IoT devices are properly connected and configured."
- Clean, professional interface ready for real-time data visualization

### Figma Mockups
*[Figma design files will be added here]*

### Circuit Diagrams
*[IoT device integration diagrams will be added here]*

## 🚀 Deployment Plan

### Phase 1: Development Environment Setup
- [x] Local development environment configuration
- [x] Firebase project setup and configuration
- [x] ML model training and validation
- [x] Core web application features implementation

### Phase 2: Testing & Quality Assurance
- [ ] Unit testing for critical components
- [ ] Integration testing with Firebase services
- [ ] ML model validation and performance testing
- [ ] User acceptance testing
- [ ] Security audit and penetration testing

### Phase 3: Staging Deployment
- [ ] Deploy to staging environment (Vercel Preview)
- [ ] Configure staging Firebase project
- [ ] End-to-end testing in staging environment
- [ ] Performance optimization and monitoring setup
- [ ] SSL certificate configuration

### Phase 4: Production Deployment

#### 🔗 Web Application Deployment (Vercel)
```bash
# Install Vercel CLI
npm install -g vercel

# Deploy to production
vercel --prod

# Configure environment variables in Vercel dashboard
```

#### 🤖 ML Model Deployment Options

1. **Render (Recommended)**
   ```bash
   # Deploy FastAPI app to Render
   # Upload model files and create web service
   ```

2. **Firebase Cloud Functions**
   ```bash
   # Deploy ML model as Cloud Function
   firebase deploy --only functions
   ```

3. **AWS Lambda**
   ```bash
   # Package model and deploy to Lambda
   # Configure API Gateway for HTTP access
   ```

### Phase 5: Monitoring & Maintenance
- [ ] Set up application monitoring (Firebase Analytics)
- [ ] Configure error tracking (Sentry)
- [ ] Implement automated backups
- [ ] Performance monitoring and optimization
- [ ] Regular security updates and patches

### Deployment Infrastructure

#### Production Stack
- **Hosting**: Vercel (Frontend) + Render (ML API)
- **Database**: Firebase Firestore
- **Authentication**: Firebase Auth
- **CDN**: Vercel Edge Network
- **Monitoring**: Firebase Analytics + Custom dashboards
- **SSL**: Automatic SSL certificates

#### Scaling Strategy
- **Horizontal Scaling**: Auto-scaling on Vercel and Render
- **Database Optimization**: Firestore indexes and query optimization
- **Caching**: Edge caching for static assets
- **Load Balancing**: Built-in load balancing on hosting platforms

## 🔄 Current Development Status

### ✅ Completed Features
- ML model development and training (85.2% accuracy)
- Complete web application with authentication
- Vital signs management with AI integration
- Patient management system
- Real-time dashboard and analytics
- Responsive UI design
- Firebase security rules implementation

### 🚧 In Progress
- Advanced analytics and reporting features
- IoT device integration capabilities
- Mobile application development
- API rate limiting and optimization

### 📋 Future Enhancements
- Multi-factor authentication
- Advanced AI models for health predictions
- Telemedicine integration
- Blockchain for data integrity
- International localization
- Electronic Health Records (EHR) integration

## 🏥 Clinical Impact & Goals

### Primary Objectives
1. **Early Risk Detection**: Identify high-risk pregnancies before complications arise
2. **Healthcare Accessibility**: Provide quality healthcare assessment in low-resource settings
3. **Data-Driven Decisions**: Enable evidence-based clinical decision making
4. **Resource Optimization**: Efficient allocation of medical resources based on risk levels

### Target Users
- **Healthcare Providers**: Doctors, nurses, and medical professionals
- **Community Health Workers**: Field workers in remote areas
- **Pregnant Women**: Direct access to health monitoring
- **Healthcare Administrators**: System oversight and resource planning

### Success Metrics
- **Clinical Accuracy**: 85%+ prediction accuracy for risk assessment
- **User Adoption**: Healthcare providers actively using the system
- **Patient Outcomes**: Reduced maternal mortality and morbidity rates
- **System Performance**: <2 second response times for critical functions

## 🤝 Contributing

We welcome contributions to improve IyàCare! Please see our contribution guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support & Contact

For questions, support, or collaboration opportunities:

- **GitHub Issues**: [Create an issue](https://github.com/Tripp808/iyacare-app/issues)
- **Documentation**: Check the `/docs` folder for detailed guides
- **Email**: [Contact information]

## 🙏 Acknowledgments

- **Dataset**: Ahmed, M. (2020). Maternal Health Risk [Dataset]. UCI Machine Learning Repository. DOI: [10.24432/C5DP5D](https://doi.org/10.24432/C5DP5D)
- **Firebase Team**: For providing robust backend services
- **Open Source Community**: For the amazing tools and libraries
- **Healthcare Professionals**: For insights and feedback on clinical requirements

---

**⚠️ Medical Disclaimer**: This application is for educational and research purposes. All predictions should be verified by qualified medical professionals. This system is not a substitute for professional medical advice, diagnosis, or treatment. 