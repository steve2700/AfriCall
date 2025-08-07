# 🗂️ AfriCall Repository Structure

## 📁 Root Directory Structure

```
africall/
├── 📁 backend/                     # FastAPI backend service
├── 📁 frontend/                    # React.js web dashboard
├── 📁 mobile/                      # React Native mobile app
├── 📁 ai-engine/                   # AI/ML processing service
├── 📁 infrastructure/              # Docker, K8s, deployment configs
├── 📁 docs/                        # Documentation
├── 📁 scripts/                     # Utility scripts
├── 📁 tests/                       # Integration tests
├── 📄 docker-compose.yml          # Local development setup
├── 📄 docker-compose.prod.yml     # Production setup
├── 📄 README.md                   # Main project documentation
├── 📄 CONTRIBUTING.md             # Development guidelines
├── 📄 LICENSE                     # MIT License
└── 📄 .gitignore                  # Git ignore rules
```

---

## 🚀 Backend Service Structure

```
backend/
├── 📁 app/
│   ├── 📁 api/                     # API routes
│   │   ├── 📁 v1/
│   │   │   ├── 📁 endpoints/
│   │   │   │   ├── 📄 auth.py
│   │   │   │   ├── 📄 calls.py
│   │   │   │   ├── 📄 leads.py
│   │   │   │   ├── 📄 businesses.py
│   │   │   │   ├── 📄 analytics.py
│   │   │   │   └── 📄 webhooks.py
│   │   │   ├── 📄 api.py          # API router
│   │   │   └── 📄 deps.py         # Dependencies
│   │   └── 📄 __init__.py
│   ├── 📁 core/                    # Core functionality
│   │   ├── 📄 config.py           # Configuration
│   │   ├── 📄 security.py         # JWT, passwords, etc.
│   │   ├── 📄 database.py         # Database connection
│   │   ├── 📄 redis.py            # Redis connection
│   │   └── 📄 celery_app.py       # Background tasks
│   ├── 📁 models/                  # SQLAlchemy models
│   │   ├── 📄 base.py
│   │   ├── 📄 user.py
│   │   ├── 📄 business.py
│   │   ├── 📄 call_session.py
│   │   ├── 📄 lead.py
│   │   └── 📄 follow_up.py
│   ├── 📁 schemas/                 # Pydantic schemas
│   │   ├── 📄 user.py
│   │   ├── 📄 business.py
│   │   ├── 📄 call.py
│   │   ├── 📄 lead.py
│   │   └── 📄 analytics.py
│   ├── 📁 services/                # Business logic
│   │   ├── 📄 call_handler.py
│   │   ├── 📄 lead_qualification.py
│   │   ├── 📄 telephony.py
│   │   ├── 📄 notifications.py
│   │   └── 📄 analytics.py
│   ├── 📁 utils/                   # Utility functions
│   │   ├── 📄 helpers.py
│   │   ├── 📄 validators.py
│   │   └── 📄 constants.py
│   └── 📄 main.py                  # FastAPI app
├── 📁 alembic/                     # Database migrations
│   ├── 📁 versions/
│   ├── 📄 env.py
│   └── 📄 script.py.mako
├── 📁 tests/                       # Backend tests
│   ├── 📁 api/
│   ├── 📁 services/
│   ├── 📁 models/
│   ├── 📄 conftest.py
│   └── 📄 test_main.py
├── 📄 requirements.txt             # Python dependencies
├── 📄 requirements-dev.txt         # Development dependencies
├── 📄 Dockerfile                  # Docker configuration
├── 📄 .env.example                # Environment variables template
├── 📄 alembic.ini                 # Alembic configuration
└── 📄 pytest.ini                  # Testing configuration
```

---

## 🎨 Frontend Dashboard Structure

```
frontend/
├── 📁 public/
│   ├── 📄 index.html
│   ├── 📄 favicon.ico
│   └── 📄 manifest.json
├── 📁 src/
│   ├── 📁 components/              # Reusable components
│   │   ├── 📁 ui/                  # Basic UI components
│   │   │   ├── 📄 Button.tsx
│   │   │   ├── 📄 Input.tsx
│   │   │   ├── 📄 Modal.tsx
│   │   │   └── 📄 Spinner.tsx
│   │   ├── 📁 layout/              # Layout components
│   │   │   ├── 📄 Header.tsx
│   │   │   ├── 📄 Sidebar.tsx
│   │   │   └── 📄 Layout.tsx
│   │   ├── 📁 charts/              # Chart components
│   │   │   ├── 📄 CallMetrics.tsx
│   │   │   ├── 📄 LeadAnalytics.tsx
│   │   │   └── 📄 RealtimeChart.tsx
│   │   └── 📁 forms/               # Form components
│   │       ├── 📄 BusinessSetup.tsx
│   │       └── 📄 LeadForm.tsx
│   ├── 📁 pages/                   # Page components
│   │   ├── 📄 Dashboard.tsx
│   │   ├── 📄 Calls.tsx
│   │   ├── 📄 Leads.tsx
│   │   ├── 📄 Analytics.tsx
│   │   ├── 📄 Settings.tsx
│   │   └── 📄 Login.tsx
│   ├── 📁 hooks/                   # Custom React hooks
│   │   ├── 📄 useAuth.ts
│   │   ├── 📄 useApi.ts
│   │   ├── 📄 useWebSocket.ts
│   │   └── 📄 useOffline.ts
│   ├── 📁 services/                # API services
│   │   ├── 📄 api.ts
│   │   ├── 📄 auth.ts
│   │   ├── 📄 calls.ts
│   │   ├── 📄 leads.ts
│   │   └── 📄 websocket.ts
│   ├── 📁 store/                   # State management
│   │   ├── 📄 index.ts
│   │   ├── 📄 authSlice.ts
│   │   ├── 📄 callsSlice.ts
│   │   └── 📄 leadsSlice.ts
│   ├── 📁 utils/                   # Utility functions
│   │   ├── 📄 constants.ts
│   │   ├── 📄 helpers.ts
│   │   └── 📄 formatters.ts
│   ├── 📁 types/                   # TypeScript types
│   │   ├── 📄 api.ts
│   │   ├── 📄 business.ts
│   │   └── 📄 call.ts
│   ├── 📁 styles/                  # CSS/styling
│   │   ├── 📄 globals.css
│   │   └── 📄 components.css
│   ├── 📄 App.tsx                  # Main app component
│   ├── 📄 index.tsx               # Entry point
│   └── 📄 setupTests.ts           # Test setup
├── 📄 package.json                # Dependencies
├── 📄 tsconfig.json               # TypeScript config
├── 📄 tailwind.config.js          # Tailwind CSS config
├── 📄 vite.config.ts              # Vite configuration
├── 📄 .env.example                # Environment variables
└── 📄 Dockerfile                  # Docker configuration
```

---

## 📱 Mobile App Structure

```
mobile/
├── 📁 src/
│   ├── 📁 components/              # Reusable components
│   │   ├── 📁 ui/
│   │   │   ├── 📄 Button.tsx
│   │   │   ├── 📄 Input.tsx
│   │   │   ├── 📄 Card.tsx
│   │   │   └── 📄 Loading.tsx
│   │   ├── 📁 charts/
│   │   │   ├── 📄 CallChart.tsx
│   │   │   └── 📄 LeadChart.tsx
│   │   └── 📁 forms/
│   │       └── 📄 LeadForm.tsx
│   ├── 📁 screens/                 # Screen components
│   │   ├── 📄 DashboardScreen.tsx
│   │   ├── 📄 CallsScreen.tsx
│   │   ├── 📄 LeadsScreen.tsx
│   │   ├── 📄 SettingsScreen.tsx
│   │   └── 📄 LoginScreen.tsx
│   ├── 📁 navigation/              # Navigation setup
│   │   ├── 📄 AppNavigator.tsx
│   │   ├── 📄 AuthNavigator.tsx
│   │   └── 📄 TabNavigator.tsx
│   ├── 📁 services/                # Services & API
│   │   ├── 📄 api.ts
│   │   ├── 📄 offline.ts
│   │   ├── 📄 sync.ts
│   │   └── 📄 notifications.ts
│   ├── 📁 store/                   # State management (Redux)
│   │   ├── 📄 index.ts
│   │   ├── 📄 authSlice.ts
│   │   ├── 📄 offlineSlice.ts
│   │   └── 📄 syncSlice.ts
│   ├── 📁 utils/                   # Utilities
│   │   ├── 📄 constants.ts
│   │   ├── 📄 helpers.ts
│   │   └── 📄 storage.ts
│   ├── 📁 types/                   # TypeScript types
│   │   └── 📄 index.ts
│   └── 📄 App.tsx                  # Main app
├── 📁 android/                     # Android specific
├── 📁 ios/                         # iOS specific
├── 📄 package.json
├── 📄 tsconfig.json
├── 📄 metro.config.js
├── 📄 babel.config.js
└── 📄 react-native.config.js
```

---

## 🧠 AI Engine Structure

```
ai-engine/
├── 📁 src/
│   ├── 📁 models/                  # AI models
│   │   ├── 📄 speech_to_text.py
│   │   ├── 📄 text_to_speech.py
│   │   ├── 📄 intent_classifier.py
│   │   └── 📄 language_detector.py
│   ├── 📁 services/                # AI services
│   │   ├── 📄 conversation.py
│   │   ├── 📄 lead_scoring.py
│   │   ├── 📄 sentiment_analysis.py
│   │   └── 📄 voice_handler.py
│   ├── 📁 training/                # Model training
│   │   ├── 📁 data/
│   │   ├── 📁 scripts/
│   │   └── 📁 models/
│   ├── 📁 utils/                   # Utilities
│   │   ├── 📄 audio_processing.py
│   │   ├── 📄 text_processing.py
│   │   └── 📄 model_utils.py
│   └── 📄 main.py                  # FastAPI app for AI service
├── 📁 data/                        # Training data
│   ├── 📁 conversations/
│   ├── 📁 audio_samples/
│   └── 📁 language_models/
├── 📁 tests/
│   ├── 📄 test_models.py
│   └── 📄 test_services.py
├── 📄 requirements.txt
├── 📄 Dockerfile
└── 📄 README.md
```

---

## 🏗️ Infrastructure Structure

```
infrastructure/
├── 📁 docker/
│   ├── 📄 backend.Dockerfile
│   ├── 📄 frontend.Dockerfile
│   ├── 📄 ai-engine.Dockerfile
│   └── 📄 nginx.Dockerfile
├── 📁 kubernetes/
│   ├── 📄 namespace.yaml
│   ├── 📄 configmap.yaml
│   ├── 📄 secrets.yaml
│   ├── 📄 backend-deployment.yaml
│   ├── 📄 frontend-deployment.yaml
│   ├── 📄 ai-engine-deployment.yaml
│   ├── 📄 postgres-deployment.yaml
│   ├── 📄 redis-deployment.yaml
│   └── 📄 ingress.yaml
├── 📁 terraform/                   # Infrastructure as Code
│   ├── 📄 main.tf
│   ├── 📄 variables.tf
│   ├── 📄 outputs.tf
│   └── 📁 modules/
├── 📁 ansible/                     # Configuration management
│   ├── 📄 playbook.yml
│   ├── 📄 inventory.yml
│   └── 📁 roles/
├── 📁 monitoring/
│   ├── 📄 prometheus.yml
│   ├── 📄 grafana-dashboard.json
│   └── 📄 alertmanager.yml
└── 📁 scripts/
    ├── 📄 deploy.sh
    ├── 📄 backup.sh
    └── 📄 restore.sh
```

---

## 📚 Documentation Structure

```
docs/
├── 📁 api/                         # API documentation
│   ├── 📄 authentication.md
│   ├── 📄 calls.md
│   ├── 📄 leads.md
│   └── 📄 webhooks.md
├── 📁 development/                 # Developer guides
│   ├── 📄 getting-started.md
│   ├── 📄 coding-standards.md
│   ├── 📄 testing.md
│   └── 📄 deployment.md
├── 📁 user/                        # User documentation
│   ├── 📄 quick-start.md
│   ├── 📄 dashboard-guide.md
│   ├── 📄 mobile-app.md
│   └── 📄 troubleshooting.md
├── 📁 business/                    # Business documentation
│   ├── 📄 pricing.md
│   ├── 📄 features.md
│   └── 📄 roadmap.md
├── 📁 architecture/                # Technical architecture
│   ├── 📄 system-overview.md
│   ├── 📄 database-schema.md
│   ├── 📄 ai-models.md
│   └── 📄 security.md
└── 📄 README.md                    # Documentation index
```

---

## 🧪 Tests Structure

```
tests/
├── 📁 integration/                 # Cross-service tests
│   ├── 📄 test_call_flow.py
│   ├── 📄 test_lead_journey.py
│   └── 📄 test_payment_flow.py
├── 📁 e2e/                        # End-to-end tests
│   ├── 📄 test_user_journey.py
│   ├── 📄 test_mobile_app.py
│   └── 📄 test_dashboard.py
├── 📁 performance/                 # Performance tests
│   ├── 📄 test_load.py
│   ├── 📄 test_stress.py
│   └── 📄 test_concurrent_calls.py
├── 📁 fixtures/                    # Test data
│   ├── 📄 audio_samples/
│   ├── 📄 conversations.json
│   └── 📄 users.json
└── 📄 conftest.py                  # Shared test configuration
```

---

## 🛠️ Scripts Structure

```
scripts/
├── 📁 setup/                       # Setup scripts
│   ├── 📄 install-dependencies.sh
│   ├── 📄 setup-database.sh
│   ├── 📄 setup-redis.sh
│   └── 📄 create-env.sh
├── 📁 development/                 # Development tools
│   ├── 📄 start-services.sh
│   ├── 📄 stop-services.sh
│   ├── 📄 reset-database.sh
│   └── 📄 generate-test-data.py
├── 📁 deployment/                  # Deployment scripts
│   ├── 📄 deploy-staging.sh
│   ├── 📄 deploy-production.sh
│   ├── 📄 rollback.sh
│   └── 📄 health-check.sh
├── 📁 maintenance/                 # Maintenance scripts
│   ├── 📄 backup-database.sh
│   ├── 📄 cleanup-logs.sh
│   ├── 📄 update-models.py
│   └── 📄 migrate-data.py
└── 📁 monitoring/                  # Monitoring scripts
    ├── 📄 check-services.sh
    ├── 📄 alert-setup.sh
    └── 📄 log-analyzer.py
```

---

## 📦 Configuration Files

### Root Level Configuration

```yaml
# docker-compose.yml
version: '3.8'
services:
  postgres:
    image: postgres:14
    environment:
      POSTGRES_DB: africall
      POSTGRES_USER: africall
      POSTGRES_PASSWORD: ${DB_PASSWORD}
    volumes:
      - postgres_data:/var/lib/postgresql/data
    ports:
      - "5432:5432"

  redis:
    image: redis:7-alpine
    ports:
      - "6379:6379"

  backend:
    build: ./backend
    volumes:
      - ./backend:/app
    ports:
      - "8000:8000"
    depends_on:
      - postgres
      - redis
    environment:
      - DATABASE_URL=postgresql://africall:${DB_PASSWORD}@postgres:5432/africall
      - REDIS_URL=redis://redis:6379/0

  ai-engine:
    build: ./ai-engine
    volumes:
      - ./ai-engine:/app
    ports:
      - "8001:8001"
    depends_on:
      - redis

  frontend:
    build: ./frontend
    volumes:
      - ./frontend:/app
      - /app/node_modules
    ports:
      - "3000:3000"
    environment:
      - REACT_APP_API_URL=http://localhost:8000

volumes:
  postgres_data:
```

### Environment Variables Template

```bash
# .env.example
# Database
DATABASE_URL=postgresql://africall:password@localhost:5432/africall
REDIS_URL=redis://localhost:6379/0

# JWT Security
SECRET_KEY=your-super-secret-key-here
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30

# Twilio Configuration
TWILIO_ACCOUNT_SID=your_twilio_account_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_PHONE_NUMBER=+1234567890

# OpenAI Configuration
OPENAI_API_KEY=your_openai_api_key

# Email Configuration (SendGrid)
SENDGRID_API_KEY=your_sendgrid_api_key
FROM_EMAIL=no-reply@africall.com

# WhatsApp Business API
WHATSAPP_ACCESS_TOKEN=your_whatsapp_token
WHATSAPP_PHONE_NUMBER_ID=your_phone_number_id

# Mobile Money APIs
MPESA_CONSUMER_KEY=your_mpesa_consumer_key
MPESA_CONSUMER_SECRET=your_mpesa_consumer_secret
MPESA_PASSKEY=your_mpesa_passkey

# Monitoring
SENTRY_DSN=your_sentry_dsn
PROMETHEUS_PORT=9090

# Development
DEBUG=true
ENVIRONMENT=development
```

---

## 🔧 Package Configuration Examples

### Backend requirements.txt
```txt
fastapi==0.104.1
uvicorn[standard]==0.24.0
sqlalchemy==2.0.23
alembic==1.12.1
asyncpg==0.29.0
redis==5.0.1
celery==5.3.4
pydantic==2.5.0
python-jose[cryptography]==3.3.0
passlib[bcrypt]==1.7.4
python-multipart==0.0.6
httpx==0.25.2
twilio==8.10.3
openai==1.3.7
python-dotenv==1.0.0
pytest==7.4.3
pytest-asyncio==0.21.1
```

### Frontend package.json
```json
{
  "name": "africall-frontend",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@reduxjs/toolkit": "^1.9.7",
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-router-dom": "^6.18.0",
    "react-redux": "^8.1.3",
    "axios": "^1.6.2",
    "recharts": "^2.8.0",
    "socket.io-client": "^4.7.3",
    "tailwindcss": "^3.3.5",
    "@headlessui/react": "^1.7.17",
    "@heroicons/react": "^2.0.18"
  },
  "devDependencies": {
    "@types/react": "^18.2.37",
    "@types/react-dom": "^18.2.15",
    "typescript": "^5.2.2",
    "vite": "^4.5.0",
    "@vitejs/plugin-react": "^4.1.1",
    "eslint": "^8.53.0",
    "prettier": "^3.1.0"
  },
  "scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "test": "jest",
    "preview": "vite preview"
  }
}
```

---

## 🚀 Getting Started Commands

```bash
# Clone and setup
git clone https://github.com/yourusername/africall.git
cd africall

# Setup environment
cp .env.example .env
# Edit .env with your configuration

# Start all services for development
docker-compose up -d

# Setup backend
cd backend
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt
alembic upgrade head

# Setup frontend
cd ../frontend
npm install
npm run dev

# Setup mobile
cd ../mobile
npm install
npx react-native run-android  # or run-ios
```

## 🔄 Development Workflow

```bash
# Create new feature branch
git checkout -b feature/new-feature

# Make changes and test
docker-compose exec backend pytest
cd frontend && npm test
cd mobile && npm test

# Commit and push
git add .
git commit -m "Add new feature"
git push origin feature/new-feature

# Create pull request on GitHub
```

This repository structure gives you:

✅ **Clear separation of concerns**  
✅ **Scalable architecture**  
✅ **Easy development setup**  
✅ **Comprehensive testing**  
✅ **Production-ready deployment**  
✅ **African market focus**

Want me to create detailed implementation for any specific part or generate the initial project scaffolding?
