# 🤝 Rog Sarthi - NGO Volunteer Management Platform

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-Active-brightgreen)

## 📋 Overview

**Rog Sarthi** is a comprehensive web-based platform designed to connect NGOs with motivated volunteers. It streamlines the volunteer recruitment process by providing NGOs with a simple registration system and enabling volunteers to find meaningful opportunities that match their skills, availability, and interests.

The platform features:
- 🎯 Professional NGO registration forms with comprehensive volunteer requirement specifications
- 👤 Volunteer profile management and opportunity discovery
- 📱 Fully responsive design for desktop and mobile devices
- ✅ Real-time form validation with intuitive error feedback
- 🗄️ Reliable data persistence with MongoDB
- 🔐 Secure backend API with CORS protection
- 📊 Centralized volunteer data management

---

## 💡 Why Rog Sarthi?

### 1. **Streamlines NGO-Volunteer Matching**
Eliminates the traditional, time-consuming manual recruitment process. NGOs specify exact volunteer requirements (category, age group, experience level), while volunteers find opportunities perfectly suited to their skills. This enables faster, more efficient connections between organizations and committed volunteers.

### 2. **Centralized Volunteer Data Management**
Creates a unified, MongoDB-backed repository for all NGO registrations, volunteer profiles, and requirements. Organizations can easily access volunteer information, track registrations, manage requirements, and maintain detailed records—all in one place instead of scattered spreadsheets or paper-based systems.

### 3. **Reduces Barriers to Volunteerism & Improves Outreach**
A user-friendly web interface with comprehensive forms and validation makes participation effortless for both NGOs and volunteers. The responsive design ensures accessibility across all devices, while standardized data collection ensures NGOs receive consistent, quality information about available volunteers.

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| **Frontend** | HTML5, CSS3, JavaScript |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB |
| **Additional** | CORS, Body-parser, Nodemon (dev) |

---

## 📋 Features

### Registration Forms
- **NGO Registration**: Organization name, email, phone, address, contact person details
- **Volunteer Registration**: Profile information, skills, availability, interests, and experience level

### Volunteer Requirements Specification
NGOs can specify:
- Number of volunteers needed
- Category of volunteers (Blind, Deaf, Mentally Challenged, etc.)
- Age group requirements
- Required experience level
- Detailed descriptions of volunteer roles

### Data Validation
- ✅ Required field checking
- ✅ Email format validation
- ✅ Phone number validation
- ✅ Minimum character length validation
- ✅ Real-time error feedback

### Responsive Design
- Mobile-first approach
- Works seamlessly on all screen sizes
- Professional UI matching project theme

---

## 🚀 Quick Start

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn
- MongoDB (local or cloud instance)

### Installation

1. **Clone the repository**
```bash
cd d:\Rog_Sarthi
```

2. **Install dependencies**
```bash
npm install
```

This installs:
- Express.js (web server)
- Mongoose (MongoDB ODM)
- CORS (cross-origin request handling)
- Body-parser (request parsing)
- Nodemon (development auto-reload)

3. **Configure environment variables** (optional)
Create a `.env` file in the root directory:
```env
MONGODB_URI=mongodb://localhost:27017/rog_sarthi
PORT=5000
NODE_ENV=development
```

4. **Start the server**

For production:
```bash
npm start
```

For development (with auto-reload):
```bash
npm run dev
```

The server will start on `http://localhost:5000`

---

## 📖 Usage

### Access the Forms

**Option 1: Using Live Server**
- Right-click on `NGORegistrationForm.html` or `VolunteerRegistrationForm.html`
- Select "Open with Live Server"
- Forms will open in your default browser

**Option 2: Direct Access**
- Open the HTML files directly in your browser
- Ensure the backend server is running for form submissions

### Form Endpoints

#### NGO Registration
```
POST /api/register-ngo
Content-Type: application/json

{
  "ngoName": "Example NGO",
  "email": "contact@ngo.com",
  "phone": "+91-9999999999",
  "address": "Address here",
  "contactPersonName": "John Doe",
  "contactPersonEmail": "john@ngo.com",
  "volunteersNeeded": "5",
  "categoryOfVolunteers": "blind",
  "volunteerAgeGroup": "20-25",
  "experienceLevel": "1-3",
  "volunteerDescription": "Description..."
}
```

#### Volunteer Registration
```
POST /api/register-volunteer
Content-Type: application/json

{
  "fullName": "Jane Doe",
  "email": "jane@email.com",
  "phone": "+91-9999999999",
  "skills": ["Teaching", "Mentoring"],
  "availability": "Weekends",
  "experience": "2-5 years"
}
```

---

## 📁 Project Structure

```
Rog_Sarthi/
├── server.js                    # Express.js backend server
├── package.json                 # Node.js dependencies
├── nodemon.json                 # Nodemon configuration
├── index.html                   # Home page
├── LandingPage.html            # Landing page with navigation
├── NGORegistrationForm.html     # NGO registration form
├── VolunteerRegistrationForm.html # Volunteer registration form
├── script.js                    # Frontend JavaScript
├── style.css                    # Global styles
├── config/
│   └── db.js                   # Database configuration
├── models/
│   ├── NGO.js                  # NGO data model
│   └── Volunteer.js            # Volunteer data model
├── data/
│   └── mongodb/                # Local MongoDB database files
└── README.md                    # Project documentation
```

---

## 🔧 Development

### Running in Development Mode
```bash
npm run dev
```
Uses Nodemon to automatically restart the server when files change.

### Key Files to Modify
- **Backend Logic**: `server.js`
- **Database Models**: Files in `models/` directory
- **Frontend Forms**: `.html` files in root directory
- **Styling**: `style.css`

---

## 📝 API Reference

### Response Format
All API responses follow this format:
```json
{
  "success": true/false,
  "message": "Response message",
  "data": {}
}
```

### Error Handling
- Invalid requests return 400 (Bad Request)
- Server errors return 500 (Internal Server Error)
- Each response includes descriptive error messages

---

## 🎨 Frontend Features

- **Form Validation**: Real-time client-side validation
- **User Feedback**: Clear error messages and success notifications
- **Responsive UI**: Mobile-optimized layout
- **Accessibility**: Semantic HTML for screen readers

---

## 🔐 Security Considerations

- ✅ CORS protection enabled
- ✅ Input validation on both client and server
- ✅ MongoDB injection prevention (via Mongoose)
- ⚠️ Consider adding authentication for production use
- ⚠️ Implement HTTPS for live deployment

---

## 🚀 Deployment

### Local MongoDB
If using local MongoDB, ensure the service is running:
```bash
# Windows
mongod
```

### Cloud MongoDB (MongoDB Atlas)
Update the connection string in `config/db.js`:
```javascript
const mongoURI = 'mongodb+srv://username:password@cluster.mongodb.net/rog_sarthi';
```

### Hosting Options
- **Node.js Hosting**: Heroku, Railway, Render, DigitalOcean
- **Database**: MongoDB Atlas (free tier available)

---

## 📊 Data Models

### NGO Model
- Organization name, email, phone, address
- Contact person information
- Volunteer requirements and specifications
- Registration timestamp

### Volunteer Model
- Personal information (name, email, phone)
- Skills and experience level
- Availability and preferences
- Registration timestamp

---

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 💬 Support

For issues, questions, or suggestions:
- Open an issue on the project repository
- Check existing documentation
- Review the SETUP_INSTRUCTIONS.md file

---

## 🎯 Future Roadmap

- [ ] User authentication and authorization
- [ ] Advanced search and filtering for volunteers
- [ ] Email notifications for NGOs and volunteers
- [ ] Volunteer matching algorithm
- [ ] Admin dashboard for analytics
- [ ] Mobile app (React Native)
- [ ] Payment integration for donations
- [ ] Social media integration

---

## ✨ Credits

Built with ❤️ for connecting NGOs with passionate volunteers.

**Last Updated**: May 2026
