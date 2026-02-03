# 🎯 BEACON - Government Policy Intelligence Platform

**AI-powered platform for Ministry of Education (MoE) and Higher-Education institutions to retrieve, understand, compare, explain, and audit government policies.**

[![Status](https://img.shields.io/badge/status-production%20ready-brightgreen)]()
[![Version](https://img.shields.io/badge/version-2.1.0-blue)]()
[![Python](https://img.shields.io/badge/python-3.11%2B-blue)]()
[![React](https://img.shields.io/badge/react-18-blue)]()

---

## 📚 Documentation Structure

This project uses a **phase-based documentation system** for better organization:

### Core Documentation

- **README.md** (this file) - Quick start and overview
- **PROJECT_DESCRIPTION.md** - Comprehensive technical documentation

### Phase Documentation

1. **PHASE_1_SETUP_AND_AUTHENTICATION.md** (7 documents)
   - Email verification system
   - Two-step registration
   - University email domain validation
   - Authentication setup guides

2. **PHASE_2_DOCUMENT_MANAGEMENT.md** (15 documents)
   - Document approval workflows
   - Draft and review processes
   - Access control and security
   - Status visibility and badges
   - Search and sorting features

3. **PHASE_3_INSTITUTION_AND_ROLE_MANAGEMENT.md** (22 documents)
   - Institution hierarchy management
   - Ministry and university relationships
   - Role-based permissions
   - Institution deletion workflows
   - User management strategies

4. **PHASE_4_ADVANCED_FEATURES_AND_OPTIMIZATIONS.md** (61 documents)
   - Chat system and voice queries
   - Notification system
   - RAG and vector store optimizations
   - Performance improvements (Redis, caching, indexing)
   - External data sources
   - Analytics and insights
   - UI/UX fixes and enhancements
   - Security audits and fixes

---

## ✨ Key Features

### 🤖 AI-Powered Intelligence (Google Services)

- 🧠 **Gemini 2.5 Flash:** Latest Google AI for advanced reasoning and policy analysis
- 🎤 **Voice Queries:** Google Speech-to-Text API supporting 98+ languages
- 👁️ **Smart OCR:** Google Cloud Vision API for text extraction from images and PDFs
- 🌍 **Multilingual:** 100+ languages including Hindi, Tamil, Telugu, Bengali
- 📊 **Policy Analysis:** Compare documents, detect conflicts, check compliance
- 🔍 **Contextual Search:** Understand intent and provide relevant answers

### 📄 Document Management

- 📁 **Multi-format Support:** PDF, DOCX, PPTX, Images (with Google OCR)
- 🔍 **Hybrid Search:** Semantic + keyword search with intelligent ranking
- ⚡ **Lazy RAG:** Instant uploads, on-demand embedding for faster processing
- 📚 **Citation Tracking:** All AI answers include source documents with page numbers
- 🔐 **Role-Based Access:** Hierarchical document visibility and permissions
- 📋 **Document Families:** Group related documents for better organization

### 👥 User & Institution Management

- 🏛️ **Role Hierarchy:** Developer → Ministry Admin → University Admin → Document Officer → Student
- 🏢 **Institution Types:** Universities, Hospitals, Research Centers, Defense Academies
- ✅ **Approval Workflows:** Multi-level document and user approval system
- 📧 **Email Verification:** Secure two-step registration with domain validation
- 🔔 **Smart Notifications:** Contextual alerts based on role and activity

### 🚀 Advanced Features

- 📱 **Mobile-First:** Responsive design optimized for all devices
- 🔔 **Real-time Notifications:** Hierarchical notification routing system
- 📈 **Analytics Dashboard:** System health, activity tracking, user insights
- 🔗 **External Data Sync:** Connect to ministry databases and APIs
- 🎨 **Theme Support:** Light/dark mode with persistent user preferences
- 💬 **Live Chat:** Real-time AI assistant with conversation history

---

## 🚀 Quick Start

### Prerequisites

- Python 3.11+
- PostgreSQL 15+ with pgvector extension
- Node.js 18+
- Supabase account (or S3-compatible storage)
- Google API key (Gemini)

### 1. Clone Repository

```bash
git clone <repository-url>
cd Beacon__V1
```

### 2. Backend Setup

```bash
# Create virtual environment
python -m venv venv

# Activate (Windows)
venv\Scripts\activate

# Activate (Linux/Mac)
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 3. Configure Environment

Create `.env` file in root directory:

```env
# Database
DATABASE_HOSTNAME=your-db-host
DATABASE_PORT=5432
DATABASE_NAME=postgres
DATABASE_USERNAME=your-username
DATABASE_PASSWORD=your-password

# Supabase Storage
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_KEY=your-supabase-key
SUPABASE_BUCKET_NAME=Docs

# AI Service
GOOGLE_API_KEY=your-google-api-key

# JWT Authentication
JWT_SECRET_KEY=your-secret-key
JWT_ALGORITHM=HS256
JWT_EXPIRATION_MINUTES=1440

# Email (Optional - for verification)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASSWORD=your-app-password
FROM_EMAIL=your-email@gmail.com
FROM_NAME=BEACON System
FRONTEND_URL=http://localhost:5173

# Redis (Optional - for caching)
REDIS_URL=redis://localhost:6379
```

### 4. Database Setup

```bash
# Enable pgvector extension
python scripts/enable_pgvector.py

# Run migrations
alembic upgrade head

# Initialize developer account (optional)
python backend/init_developer.py
```

### 5. Start Backend

```bash
uvicorn backend.main:app --reload --host 127.0.0.1 --port 8000
```

Backend will be available at: http://localhost:8000

### 6. Frontend Setup

```bash
cd frontend

# Install dependencies
npm install

# Create .env file
echo "VITE_API_BASE_URL=http://localhost:8000/api" > .env

# Start development server
npm run dev
```

Frontend will be available at: http://localhost:5173

---

## 🎯 Demo Account

For quick testing and demonstration purposes, a demo account is automatically created:

**Demo Credentials:**

```
Email: demo@beacon.system
Password: demo123
Role: Student
```

**What you can test:**

- ✅ Login functionality
- ✅ Document browsing and search
- ✅ AI chat with document queries
- ✅ Mobile responsiveness
- ✅ Voice queries (if microphone available)

**Create Demo Account Manually:**

```bash
# Run the demo account script
python scripts/create_demo_account.py

# Or on Windows
scripts/create_demo_account.bat
```

> **Note**: This is a demo account with limited permissions. It cannot upload documents or access admin features.

---

## 🚀 New Features & Google Services Integration

### 🤖 Google AI Services

**Gemini 2.5 Flash Integration:**

- 🧠 **Advanced Reasoning:** Latest Gemini model for complex policy analysis
- 🌍 **Multilingual Support:** 100+ languages including Indian regional languages
- ⚡ **Fast Response:** Optimized for real-time chat interactions
- 📊 **Context Awareness:** Understands document relationships and policy implications

**Google Cloud Vision API:**

- 📸 **OCR Processing:** Extract text from images and scanned documents
- 🔍 **Handwriting Recognition:** Process handwritten notes and forms
- 📄 **PDF Text Extraction:** Advanced text extraction from complex PDFs
- 🌐 **Multi-language OCR:** Support for Hindi, Tamil, Telugu, Bengali, and more

**Google Speech-to-Text API:**

- 🎤 **Voice Queries:** Ask questions in natural language via audio
- 🗣️ **98+ Languages:** Support for major world languages
- 🎯 **High Accuracy:** Advanced speech recognition with punctuation
- 📱 **Real-time Processing:** Live transcription for instant responses

### 🆕 Latest Features (v2.0.0)

**Enhanced Document Management:**

- 📚 **Document Families:** Group related documents for better organization
- 🔄 **Version Control:** Track document updates and changes
- 🏷️ **Smart Tagging:** Auto-categorization based on content analysis
- 📋 **Batch Operations:** Upload and process multiple documents simultaneously

**Advanced AI Capabilities:**

- 🧩 **Policy Comparison:** Side-by-side analysis of government policies
- ⚠️ **Conflict Detection:** Identify contradictions between documents
- ✅ **Compliance Checking:** Verify adherence to regulations and guidelines
- 📈 **Trend Analysis:** Track policy changes over time

**Smart Search & Retrieval:**

- 🔍 **Hybrid Search:** Combines semantic and keyword search for better results
- 🎯 **Contextual Ranking:** Results ranked by relevance and user role
- 📊 **Search Analytics:** Track popular queries and document access patterns
- 🔗 **Citation Tracking:** Full source attribution for all AI responses

**Mobile-First Design:**

- 📱 **Responsive UI:** Optimized for mobile devices and tablets
- 👆 **Touch-Friendly:** Intuitive gestures and mobile navigation
- 🔄 **Offline Support:** Basic functionality works without internet
- 📲 **PWA Ready:** Install as a mobile app

**Real-time Collaboration:**

- 💬 **Live Chat:** Real-time messaging with AI assistant
- 🔔 **Smart Notifications:** Contextual alerts based on user role and interests
- 👥 **Team Workspaces:** Collaborative document review and approval
- 📊 **Activity Feeds:** Track team actions and document changes

**Enterprise Security:**

- 🔐 **Zero-Trust Architecture:** Verify every request and user
- 🛡️ **Data Encryption:** End-to-end encryption for sensitive documents
- 📋 **Audit Trails:** Complete logging of all user actions
- 🔒 **Role-Based Access:** Granular permissions based on organizational hierarchy

### 🌟 Google Cloud Integration Benefits

**Scalability:**

- ☁️ **Auto-scaling:** Handle varying loads automatically
- 🌍 **Global CDN:** Fast document access worldwide
- 💾 **Unlimited Storage:** Scale storage as needed
- ⚡ **Edge Computing:** Reduced latency with global edge locations

**Reliability:**

- 🔄 **99.9% Uptime:** Enterprise-grade availability
- 🔧 **Auto-healing:** Self-recovering infrastructure
- 📊 **Health Monitoring:** Proactive issue detection
- 🔒 **Data Backup:** Automated backups and disaster recovery

**Cost Optimization:**

- 💰 **Pay-per-use:** Only pay for what you consume
- 📊 **Usage Analytics:** Track and optimize costs
- 🎯 **Smart Quotas:** Prevent unexpected charges
- 💡 **Free Tier:** Generous free usage limits

---

## 🏗️ System Architecture

### Technology Stack

**Backend:**

- FastAPI (Python 3.11+)
- PostgreSQL with pgvector extension
- SQLAlchemy ORM with Alembic migrations
- JWT authentication with role-based access
- Redis caching for performance optimization

**Frontend:**

- React 18 with Vite build system
- TailwindCSS + shadcn/ui components
- Zustand state management
- React Router v6 with protected routes
- Axios for API calls with interceptors

**Google Cloud AI Services:**

- 🧠 **Gemini 2.5 Flash:** Advanced LLM for reasoning and analysis
- 🎤 **Speech-to-Text API:** Voice query processing (98+ languages)
- 👁️ **Cloud Vision API:** OCR and image text extraction
- 🌍 **Translation API:** Multi-language document support
- ☁️ **Cloud Storage:** Scalable document storage

**AI/ML Stack:**

- BGE-M3 embeddings (multilingual, 1024-dim)
- pgvector for similarity search
- Hybrid retrieval (semantic + keyword)
- Lazy embedding strategy for performance
- Citation tracking and source attribution

**Infrastructure:**

- Supabase (PostgreSQL + Storage)
- Vercel (Frontend hosting)
- Render (Backend hosting)
- Upstash Redis (Caching)
- UptimeRobot (Monitoring)

### RAG Architecture

```
Upload → Process → Extract Metadata → Store
                                        ↓
Query → Search Metadata → Rerank → Embed (if needed) → Search → Answer + Citations
```

**Lazy Embedding Strategy:**

- Documents uploaded instantly (no waiting for embedding)
- Embeddings generated on first query
- Subsequent queries use cached embeddings
- Multi-machine support via PostgreSQL storage

---

## 👥 User Roles & Hierarchy

```
Developer (Super Admin)
    ↓
Ministry Admin (MoE Officials)
    ↓
University Admin (Institution Heads)
    ↓
Document Officer (Upload/Manage Docs)
    ↓
Student (Read-Only Access)
    ↓
Public Viewer (Limited Access)
```

### Role Permissions

| Feature            | Developer | Ministry Admin     | University Admin    | Document Officer    | Student     |
| ------------------ | --------- | ------------------ | ------------------- | ------------------- | ----------- |
| View all documents | ✅        | ✅ (restricted)    | ✅ (institution)    | ✅ (institution)    | ✅ (public) |
| Upload documents   | ✅        | ✅ (auto-approved) | ✅ (needs approval) | ✅ (needs approval) | ❌          |
| Approve documents  | ✅        | ✅                 | ✅ (institution)    | ❌                  | ❌          |
| Manage users       | ✅        | ✅ (limited)       | ✅ (institution)    | ❌                  | ❌          |
| System health      | ✅        | ❌                 | ❌                  | ❌                  | ❌          |
| Analytics          | ✅        | ✅                 | ✅ (institution)    | ❌                  | ❌          |

---

## 📡 API Endpoints

### Authentication

- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/verify-email/{token}` - Email verification
- `GET /api/auth/me` - Get current user

### Documents

- `POST /api/documents/upload` - Upload document
- `GET /api/documents/list` - List documents (role-filtered)
- `GET /api/documents/{id}` - Get document details
- `GET /api/documents/{id}/download` - Download document
- `DELETE /api/documents/{id}` - Delete document

### Approvals

- `GET /api/approvals/pending` - Get pending documents
- `POST /api/approvals/{id}/approve` - Approve document
- `POST /api/approvals/{id}/reject` - Reject document

### Chat & AI

- `POST /api/chat/query` - Ask AI question
- `POST /api/voice/query` - Voice query (audio upload)
- `GET /api/chat/sessions` - Get chat history

### Institutions

- `GET /api/institutions/list` - List institutions
- `POST /api/institutions/create` - Create institution
- `DELETE /api/institutions/{id}` - Delete institution

### Notifications

- `GET /api/notifications/list` - List notifications
- `GET /api/notifications/unread-count` - Unread count
- `POST /api/notifications/{id}/mark-read` - Mark as read

### Analytics

- `GET /api/analytics/stats` - System statistics
- `GET /api/analytics/activity` - Activity feed
- `GET /api/audit/logs` - Audit logs

**Full API Documentation:** http://localhost:8000/docs

---

## 🧪 Testing

```bash
# Run all tests
python tests/run_all_tests.py

# Individual tests
python tests/test_embeddings.py
python tests/test_voice_query.py
python tests/test_multilingual_embeddings.py
python tests/test_compliance_api.py
python tests/test_conflict_detection_api.py
```

---

## 📊 Performance Metrics

| Operation           | Time   | Notes              |
| ------------------- | ------ | ------------------ |
| Document Upload     | 3-7s   | Instant response   |
| Query (embedded)    | 4-7s   | Fast               |
| Query (first time)  | 12-19s | Includes embedding |
| Voice transcription | 5-10s  | 1 min audio        |
| User Login          | <1s    | JWT generation     |

---

## 🔐 Security Features

- ✅ JWT-based authentication
- ✅ Email verification required
- ✅ Role-based access control (RBAC)
- ✅ Document-level permissions
- ✅ Audit logging for all actions
- ✅ SQL injection prevention (SQLAlchemy ORM)
- ✅ XSS protection (React escaping)
- ✅ Soft deletes (preserve audit trail)

---

## 📁 Project Structure

```
Beacon__V1/
├── Agent/                      # AI/ML Components
│   ├── embeddings/            # BGE-M3 embeddings
│   ├── voice/                 # Whisper transcription
│   ├── rag_agent/             # ReAct agent
│   ├── retrieval/             # Hybrid search
│   ├── lazy_rag/              # On-demand embedding
│   ├── vector_store/          # pgvector integration
│   └── tools/                 # Search tools
│
├── backend/                    # FastAPI Backend
│   ├── routers/               # API endpoints
│   ├── utils/                 # Helper functions
│   ├── database.py            # SQLAlchemy models
│   └── main.py                # FastAPI app
│
├── frontend/                   # React Frontend
│   ├── src/
│   │   ├── components/        # Reusable components
│   │   ├── pages/             # Route pages
│   │   ├── services/          # API calls
│   │   └── stores/            # Zustand stores
│   └── package.json
│
├── alembic/                    # Database migrations
├── scripts/                    # Utility scripts
├── tests/                      # Test suite
├── .env                        # Environment variables
├── requirements.txt            # Python dependencies
├── README.md                   # This file
└── PROJECT_DESCRIPTION.md      # Detailed documentation
```

---

## 🐛 Troubleshooting

### Database Connection Issues

```bash
# Check PostgreSQL is running
psql -h HOST -U USER -d DATABASE

# Verify .env file has correct credentials
# Test connection: python test_redis_connection.py
```

### GPU Not Detected

```bash
# Install PyTorch with CUDA support
pip install torch --index-url https://download.pytorch.org/whl/cu118
```

### Voice Not Working

```bash
# Install FFmpeg
# Windows: Download from https://ffmpeg.org/download.html
# Linux: sudo apt install ffmpeg
# Mac: brew install ffmpeg
```

### Email Verification Not Sending

```bash
# For Gmail:
# 1. Enable 2-Factor Authentication
# 2. Generate App Password: https://myaccount.google.com/apppasswords
# 3. Use App Password as SMTP_PASSWORD in .env
```

---

## 🔄 Recent Updates

### Version 2.1.0 (February 2026)

- ✅ Multi-LLM provider support (Groq, Gemini, OpenRouter, Ollama)
- ✅ Query routing for simple vs complex queries
- ✅ Document synthesis when max iterations hit
- ✅ Enhanced RAG agent performance with caching
- ✅ Mock data for Notes and OCR Review pages
- ✅ Improved error handling with user-friendly messages

### Version 2.0.0 (December 2025)

- ✅ Migrated from FAISS to pgvector for multi-machine support
- ✅ Implemented lazy RAG for instant document uploads
- ✅ Added email verification system
- ✅ Enhanced notification system with hierarchical routing
- ✅ Improved analytics dashboard with system health monitoring
- ✅ Optimized performance with Redis caching
- ✅ Added voice query support (98+ languages)
- ✅ Implemented document approval workflows
- ✅ Enhanced role-based access control

---

## 📞 Support

- **Documentation:** See phase documentation files for detailed guides
- **API Docs:** http://localhost:8000/docs
- **Logs:** `Agent/agent_logs/`
- **Tests:** `python tests/run_all_tests.py`

---

## 🎯 Key Achievements

✅ Multi-format document processing  
✅ Multilingual embeddings (100+ languages)  
✅ Voice query system (98+ languages)  
✅ Lazy RAG (instant uploads)  
✅ Hybrid retrieval (semantic + keyword)  
✅ External data ingestion  
✅ Citation tracking  
✅ Production-ready

---

**Built with ❤️ for Government Policy Intelligence**

**Version:** 2.1.0 | **Status:** ✅ Production Ready | **Last Updated:** February 3, 2026
