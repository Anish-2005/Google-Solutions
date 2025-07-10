# Financer Backend

A robust FastAPI-based backend service for the Financer application, providing authentication, financial data processing, and AI-powered insights.

## 🚀 Features

- **Firebase Authentication**: Secure user registration and login
- **NSE Data Integration**: Real-time stock market data from National Stock Exchange
- **AI Financial Advisor**: Google Generative AI powered chatbot for financial guidance
- **RESTful API**: Clean, well-documented API endpoints
- **CORS Support**: Cross-origin resource sharing for frontend integration
- **Real-time Data**: Live stock prices and market information
- **Secure Configuration**: Environment-based configuration management

## 🛠️ Tech Stack

- **FastAPI**: Modern, fast web framework for building APIs
- **Firebase Admin**: Authentication and user management
- **Google Generative AI**: AI-powered financial insights
- **Pyrebase4**: Firebase Python SDK
- **Uvicorn**: Lightning-fast ASGI server
- **Python-dotenv**: Environment variable management
- **Requests**: HTTP library for external API calls

## 📁 Project Structure

```
financer-backend/
├── main.py             # Main FastAPI application
├── models.py           # Pydantic data models
├── nse_data.py         # NSE stock data integration
├── test.py             # Testing utilities
├── requirements.txt    # Python dependencies
├── vercel.json         # Vercel deployment configuration
└── .env               # Environment variables (create this)
```

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- pip package manager
- Firebase project setup
- Google Generative AI API key

### Installation

1. **Navigate to the backend directory**
   ```bash
   cd financer-backend
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv financer-env
   
   # Activate virtual environment
   # Windows:
   financer-env\Scripts\activate
   # macOS/Linux:
   source financer-env/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Create environment file**
   Create a `.env` file in the backend root directory with your configuration (see Configuration section)

5. **Start the development server**
   ```bash
   uvicorn main:app --reload
   ```

6. **Access the API**
   - API Documentation: `http://localhost:8000/`
   - Interactive API Docs: `http://localhost:8000/docs`
   - Alternative Docs: `http://localhost:8000/redoc`

## 🔧 Configuration

### Environment Variables

Create a `.env` file in the backend root directory:

```env
# Firebase Configuration
FIREBASE_API_KEY=your_firebase_api_key
FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
FIREBASE_PROJECT_ID=your_project_id
FIREBASE_STORAGE_BUCKET=your_project.appspot.com
FIREBASE_MESSAGING_SENDER_ID=your_messaging_sender_id
FIREBASE_APP_ID=your_app_id
FIREBASE_MEASUREMENT_ID=your_measurement_id

# Firebase Service Account (JSON string)
FIREBASE_CREDENTIALS_JSON={"type": "service_account", "project_id": "...", ...}

# Google AI Configuration
GOOGLE_API_KEY=your_google_generative_ai_api_key

# Optional: Database URL
DATABASE_URL=your_database_url
```

### Firebase Setup

1. Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)
2. Enable Authentication and choose sign-in methods
3. Generate a service account key (JSON) for admin access
4. Add the service account JSON as a string to `FIREBASE_CREDENTIALS_JSON`

### Google AI Setup

1. Get an API key from [Google AI Studio](https://aistudio.google.com/)
2. Add the key to `GOOGLE_API_KEY` in your `.env` file

## 📚 API Documentation

### Authentication Endpoints

#### Sign Up
```
POST /signup
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "securepassword"
}
```

#### Login
```
POST /login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "securepassword"
}
```

### Stock Data Endpoints

#### Get Stock Information
```
GET /stocks/{symbol}
```

#### Get Stock Price
```
GET /stocks/{symbol}/price
```

### AI Chat Endpoint

#### Chat with Financial Advisor
```
POST /chat
Content-Type: application/json

{
  "message": "What should I invest in?",
  "user_id": "user123"
}
```

### Health Check

#### Server Status
```
GET /health
```

## 🗂️ Data Models

### SignUpSchema
```python
class SignUpSchema(BaseModel):
    email: str
    password: str
```

### LoginSchema
```python
class LoginSchema(BaseModel):
    email: str
    password: str
```

### ChatRequest
```python
class ChatRequest(BaseModel):
    message: str
    user_id: Optional[str] = None
```

## 📊 NSE Data Integration

The backend integrates with the National Stock Exchange (NSE) to provide:

- Real-time stock prices
- Historical stock data
- Market indices
- Company information
- Trading volumes

### Supported Features

- Stock symbol lookup
- Price history
- Market trends
- Company fundamentals

## 🤖 AI Financial Advisor

The AI chatbot provides:

- **Investment Advice**: Personalized investment recommendations
- **Market Analysis**: Analysis of market trends and opportunities
- **Portfolio Optimization**: Suggestions for portfolio improvement
- **Risk Assessment**: Risk analysis for investment decisions
- **Financial Planning**: Long-term financial planning guidance

### AI Capabilities

- Natural language processing
- Context-aware responses
- Financial knowledge base
- Personalized recommendations
- Real-time market integration

## 🔒 Security Features

- **JWT Token Authentication**: Secure API access
- **Firebase Security Rules**: Database-level security
- **CORS Configuration**: Controlled cross-origin access
- **Environment Variables**: Secure configuration management
- **Input Validation**: Pydantic model validation
- **Error Handling**: Secure error responses

## 🚀 Deployment

### Vercel Deployment

The backend is configured for Vercel deployment with `vercel.json`:

```json
{
  "version": 2,
  "builds": [
    {
      "src": "main.py",
      "use": "@vercel/python"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "main.py"
    }
  ]
}
```

### Deployment Steps

1. **Install Vercel CLI**
   ```bash
   npm i -g vercel
   ```

2. **Deploy**
   ```bash
   vercel
   ```

3. **Set Environment Variables**
   Configure all environment variables in the Vercel dashboard

### Alternative Deployment Options

- **Heroku**: Use `Procfile` with `web: uvicorn main:app --host=0.0.0.0 --port=${PORT:-5000}`
- **AWS Lambda**: Use Mangum for serverless deployment
- **Google Cloud Run**: Containerized deployment
- **DigitalOcean App Platform**: Simple deployment platform

## 🧪 Testing

### Running Tests

```bash
python test.py
```

### Test Coverage

The testing suite covers:
- Authentication endpoints
- Stock data retrieval
- AI chat functionality
- Error handling
- Input validation

### Manual Testing

Use the interactive API documentation at `/docs` to test endpoints manually.

## 📦 Dependencies

### Production Dependencies

```
fastapi              # Web framework
uvicorn             # ASGI server
pyrebase4           # Firebase Python SDK
firebase-admin      # Firebase Admin SDK
requests            # HTTP client
python-dotenv       # Environment variables
google-generativeai # Google AI SDK
setuptools          # Package tools
```

### Development Dependencies

```
pytest              # Testing framework
black               # Code formatter
flake8              # Code linter
mypy                # Type checker
```

## 🐛 Troubleshooting

### Common Issues

1. **Firebase Authentication Errors**
   ```
   Error: Invalid API key or configuration
   Solution: Verify Firebase configuration in .env file
   ```

2. **Google AI API Errors**
   ```
   Error: API key not valid
   Solution: Check GOOGLE_API_KEY in environment variables
   ```

3. **CORS Errors**
   ```
   Error: Cross-origin request blocked
   Solution: Verify CORS configuration in main.py
   ```

4. **Module Import Errors**
   ```
   Error: Module not found
   Solution: Ensure virtual environment is activated and dependencies installed
   ```

### Debug Mode

Enable debug mode for detailed error messages:

```bash
uvicorn main:app --reload --log-level debug
```

## 📈 Performance Optimization

- **Async Operations**: FastAPI's async support for concurrent requests
- **Caching**: Implement Redis for frequently accessed data
- **Database Optimization**: Query optimization and indexing
- **API Rate Limiting**: Implement rate limiting for external APIs
- **Response Compression**: Enable gzip compression

## 🔄 API Versioning

Future versions will include:
- `/v1/` prefix for current API
- `/v2/` for future enhancements
- Backward compatibility support

## 🤝 Contributing

1. Follow PEP 8 style guidelines
2. Add type hints to all functions
3. Include docstrings for modules and functions
4. Write tests for new features
5. Update API documentation
6. Use meaningful commit messages

## 📄 License

This project is part of the Financer application and follows the same license as the main repository.

## 🆘 Support

For issues and questions:
1. Check the troubleshooting section
2. Review the API documentation
3. Create an issue in the GitHub repository
4. Contact the development team
