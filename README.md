# CareConnect - Secure Telehealth Platform

A comprehensive, HIPAA-compliant telehealth platform with end-to-end encryption, built with React, TypeScript, Node.js, and PostgreSQL.

## 🏥 Features

### Healthcare Modules
- **Virtual Oncology Consultation** - Secure video consultations with specialists
- **Care Plans & Symptom Tracking** - Personalized care management and health monitoring
- **Mental Health & Peer Support** - Therapy sessions and community support
- **Educational Library** - Comprehensive health resources and guides
- **Caregiver Support** - Tools and resources for caregivers
- **Reminders & Wearables** - Smart notifications and device integration

### User Roles
- **Patients** - Access care plans, schedule appointments, track symptoms
- **Healthcare Providers** - Manage patients, update records, conduct consultations
- **Caregivers** - Monitor patient status, communicate with providers
- **System Administrators** - Manage users, configure system settings

## 🔒 Security Features

- **End-to-End Encryption** - AES-256 for data, RSA-2048 for key exchange
- **HIPAA Compliance** - Complete audit trails and secure data handling
- **Role-Based Access Control** - Granular permissions system
- **Session Management** - Secure JWT-based authentication
- **Rate Limiting** - Protection against abuse and attacks
- **Audit Logging** - Complete activity tracking

## 🛠 Technology Stack

### Frontend
- React 18 with TypeScript
- Tailwind CSS for styling
- React Router for navigation
- Lucide React for icons

### Backend
- Node.js with Express
- TypeScript for type safety
- PostgreSQL with PLpgSQL stored procedures
- JWT authentication
- Comprehensive input validation

### Security
- Helmet.js for security headers
- CORS configuration
- Rate limiting
- Input sanitization
- Encrypted data storage

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- PostgreSQL 14+
- npm or yarn

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd careconnect-platform
   ```

2. **Install frontend dependencies**
   ```bash
   npm install
   ```

3. **Install backend dependencies**
   ```bash
   cd server
   npm install
   ```

4. **Set up environment variables**
   ```bash
   # Copy example environment file
   cp server/.env.example server/.env
   
   # Edit the .env file with your configuration
   nano server/.env
   ```

5. **Set up the database**
   ```bash
   # Create PostgreSQL database
   createdb careconnect_db
   
   # Run migrations (execute SQL files in order)
   psql -d careconnect_db -f supabase/migrations/create_database_schema.sql
   psql -d careconnect_db -f supabase/migrations/create_stored_procedures.sql
   ```

6. **Start the development servers**
   ```bash
   # Start backend (from server directory)
   cd server
   npm run dev
   
   # Start frontend (from root directory)
   npm run dev
   ```

## 📊 Database Schema

The platform uses a comprehensive PostgreSQL schema with:

- **Users & Authentication** - Secure user management with encrypted PII
- **Healthcare Providers** - Provider profiles and specializations
- **Patients** - Medical records and health information
- **Appointments** - Scheduling and management system
- **Care Plans** - Treatment protocols and goals
- **Messages** - Secure communication system
- **Audit Logs** - Complete activity tracking
- **File Attachments** - Encrypted file storage

## 🔐 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/refresh` - Token refresh
- `POST /api/auth/logout` - User logout

### Users
- `GET /api/users/profile` - Get user profile
- `GET /api/users/patient/:id/medical-profile` - Get patient medical data
- `GET /api/users/search` - Search users (admin only)

### Appointments
- `POST /api/appointments` - Schedule appointment
- `GET /api/appointments` - Get user appointments
- `PUT /api/appointments/:id/status` - Update appointment
- `DELETE /api/appointments/:id` - Cancel appointment

### Care Plans
- `POST /api/care-plans` - Create care plan
- `GET /api/care-plans/patient/:id` - Get patient care plans
- `PUT /api/care-plans/:id` - Update care plan

### Messages
- `POST /api/messages` - Send message
- `GET /api/messages` - Get messages
- `PUT /api/messages/:id/read` - Mark as read

## 🏗 Architecture

### Frontend Architecture
- Component-based React architecture
- TypeScript for type safety
- Responsive design with Tailwind CSS
- Client-side routing with React Router

### Backend Architecture
- RESTful API design
- Layered architecture (routes, middleware, services)
- Database abstraction with connection pooling
- Comprehensive error handling

### Security Architecture
- Multi-layer encryption (AES + RSA)
- Role-based access control
- Session management with JWT
- Audit logging for compliance

## 🧪 Development

### Code Structure
```
├── src/                    # Frontend source
│   ├── components/         # Reusable components
│   ├── pages/             # Page components
│   ├── types/             # TypeScript types
│   └── App.tsx            # Main app component
├── server/                # Backend source
│   ├── src/
│   │   ├── routes/        # API routes
│   │   ├── middleware/    # Express middleware
│   │   ├── config/        # Configuration files
│   │   └── types/         # TypeScript types
│   └── package.json
└── supabase/migrations/   # Database migrations
```

### Environment Variables
```bash
# Database
DATABASE_URL=postgresql://user:pass@localhost:5432/careconnect_db

# JWT Secrets
JWT_SECRET=your-jwt-secret
JWT_REFRESH_SECRET=your-refresh-secret

# Encryption
ENCRYPTION_KEY=your-32-char-encryption-key

# Server
PORT=5000
NODE_ENV=development
CORS_ORIGIN=http://localhost:5173
```

## 📝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Support

For support and questions:
- Create an issue in the repository
- Contact the development team
- Check the documentation

## 🔄 Deployment

The platform can be deployed to various cloud providers:
- Frontend: Netlify, Vercel, or any static hosting
- Backend: Heroku, AWS, Google Cloud, or any Node.js hosting
- Database: PostgreSQL on AWS RDS, Google Cloud SQL, or similar

Make sure to:
1. Set up environment variables in production
2. Configure SSL certificates
3. Set up database backups
4. Configure monitoring and logging
5. Implement proper CI/CD pipelines

---

Built with ❤️ for better healthcare accessibility and security.