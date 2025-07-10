# Financer Frontend

A modern React-based frontend application for personal finance management, built with Vite and featuring a beautiful, responsive UI.

## 🎨 Features

- **Modern UI/UX**: Clean, intuitive interface with smooth animations
- **Responsive Design**: Works seamlessly across desktop, tablet, and mobile devices
- **Real-time Data Visualization**: Interactive charts and graphs for financial data
- **Secure Authentication**: Firebase-based user authentication
- **Route Protection**: Secure navigation with authentication guards
- **Fast Performance**: Built with Vite for lightning-fast development and builds

## 🛠️ Tech Stack

- **React 19**: Latest version of React with modern features
- **Vite**: Ultra-fast build tool and development server
- **React Router DOM**: Client-side routing and navigation
- **Framer Motion**: Smooth animations and transitions
- **Recharts**: Modern charting library for React
- **React Chart.js 2**: Additional charting capabilities
- **Heroicons**: Beautiful SVG icons
- **CSS Modules**: Scoped styling

## 📁 Project Structure

```
src/
├── pages/              # Application pages/routes
│   ├── LandingPage.jsx    # Welcome and authentication page
│   ├── HomePage.jsx       # Main dashboard
│   ├── AuthPage.jsx       # Login/Sign up page
│   ├── ExpensesPage.jsx   # Expense tracking page
│   ├── StocksPage.jsx     # Stock market data page
│   ├── ComparisonsPage.jsx # Stock comparison tools
│   ├── PortfoliosPage.jsx # Portfolio management
│   ├── FDPage.jsx         # Fixed deposit calculator
│   └── ChatbotPage.jsx    # AI financial advisor
├── assets/             # Static assets (images, icons)
├── App.jsx            # Main application component
├── App.css            # Global styles
├── main.jsx           # Application entry point
└── index.css          # Base CSS styles
```

## 🚀 Getting Started

### Prerequisites

- Node.js (v18 or higher)
- npm or yarn package manager

### Installation

1. **Navigate to the frontend directory**
   ```bash
   cd financer
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   npm run dev
   ```

4. **Open your browser**
   Navigate to `http://localhost:5173` to view the application

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build locally
- `npm run lint` - Run ESLint for code quality

## 🔧 Configuration

### Environment Variables

Create a `.env` file in the frontend root directory:

```env
VITE_FIREBASE_API_KEY=your_firebase_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
VITE_FIREBASE_APP_ID=your_app_id
VITE_FIREBASE_MEASUREMENT_ID=your_measurement_id
VITE_API_BASE_URL=http://localhost:8000
```

### Vite Configuration

The project uses a custom Vite configuration (`vite.config.js`) optimized for:
- Fast hot module replacement
- Optimized builds
- Asset handling
- Development server settings

## 📱 Pages Overview

### Landing Page
- Welcome screen with application overview
- Feature highlights
- Call-to-action for sign up/login

### Home Dashboard
- Overview of all financial tools
- Quick access to key features
- Recent activity summary

### Expense Tracking
- Add and categorize expenses
- Visual analytics with charts
- Monthly/yearly expense reports

### Stock Analysis
- Real-time stock data
- Performance charts
- Market trends

### Stock Comparisons
- Side-by-side stock analysis
- Comparative charts
- Performance metrics

### Portfolio Management
- Investment portfolio tracking
- Asset allocation visualization
- Performance analytics

### Fixed Deposit Calculator
- FD calculation tools
- Interest rate comparisons
- Maturity planning

### AI Financial Advisor
- Chat-based financial guidance
- Personalized recommendations
- AI-powered insights

## 🎨 Styling

The application uses a combination of:
- **CSS Modules**: For component-specific styles
- **Global CSS**: For application-wide styles
- **Framer Motion**: For animations and transitions
- **Responsive Design**: Mobile-first approach

### Color Scheme
- Primary: Modern blue gradient
- Secondary: Complementary accent colors
- Background: Clean white/light gray
- Text: Dark gray for readability

## 🔀 Routing

The application uses React Router DOM for navigation:

- `/` - Landing page
- `/auth` - Authentication page
- `/home` - Main dashboard
- `/expenses` - Expense tracking
- `/stocks` - Stock data
- `/comparisons` - Stock comparisons
- `/portfolios` - Portfolio management
- `/fd` - Fixed deposit calculator
- `/advisor` - AI chatbot

## 🚀 Deployment

### Production Build

```bash
npm run build
```

The build files will be generated in the `dist/` directory.

### Deployment Platforms

This application can be deployed to:
- **Vercel** (Recommended)
- **Netlify**
- **GitHub Pages**
- **AWS S3 + CloudFront**
- **Azure Static Web Apps**

### Example Vercel Deployment

1. Install Vercel CLI: `npm i -g vercel`
2. Run: `vercel`
3. Follow the prompts to deploy

## 🧪 Testing

### ESLint Configuration

The project includes ESLint configuration for:
- React best practices
- Modern JavaScript standards
- Code quality enforcement

Run linting:
```bash
npm run lint
```

## 📦 Dependencies

### Production Dependencies
- `react` & `react-dom`: Core React libraries
- `react-router-dom`: Routing solution
- `framer-motion`: Animation library
- `recharts`: Charting library
- `react-chartjs-2`: Chart.js integration
- `@heroicons/react`: Icon library

### Development Dependencies
- `vite`: Build tool
- `@vitejs/plugin-react`: React plugin for Vite
- `eslint`: Code linting
- Various ESLint plugins for React

## 🐛 Troubleshooting

### Common Issues

1. **Port already in use**
   ```bash
   # Kill process on port 5173
   npx kill-port 5173
   ```

2. **Module not found errors**
   ```bash
   # Clear node_modules and reinstall
   rm -rf node_modules package-lock.json
   npm install
   ```

3. **Build errors**
   ```bash
   # Clear Vite cache
   npm run build -- --force
   ```

## 🤝 Contributing

1. Follow the existing code structure
2. Use functional components with hooks
3. Implement responsive design
4. Add proper error handling
5. Include comments for complex logic
6. Test across different screen sizes

## 📄 License

This project is part of the Financer application and follows the same license as the main repository.
