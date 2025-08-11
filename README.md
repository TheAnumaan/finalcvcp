# CVCCP - CryptoVault Credit Protocol

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Solidity](https://img.shields.io/badge/Solidity-0.8+-orange.svg)](https://soliditylang.org/)
[![React](https://img.shields.io/badge/React-18+-61dafb.svg)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0+-3178c6.svg)](https://www.typescriptlang.org/)

## 🚀 Overview

**CVCCP (CryptoVault Credit Protocol)** is an advanced DeFi credit scoring system built on Scroll Sepolia. It provides comprehensive blockchain-based credit analysis using AI-powered algorithms to assess user financial behavior, DeFi interactions, and risk profiles.

## ✨ Features

### 🔐 Smart Contract Infrastructure
- **Credit Score Registry**: On-chain storage of credit scores and metadata
- **Data Validation**: Secure validation of blockchain data
- **Protocol Mathematics**: Advanced scoring algorithms and calculations
- **Foundry Integration**: Modern Solidity development and testing framework

### 🤖 AI-Powered Analysis
- **Gemini AI Integration**: Advanced AI analysis of DeFi behavior patterns
- **Risk Assessment**: Comprehensive risk evaluation and scoring
- **Behavioral Analysis**: Pattern recognition in transaction history
- **Recommendation Engine**: AI-driven lending and investment recommendations

### 🌐 Multi-Chain Data Aggregation
- **Alchemy Integration**: Ethereum mainnet and L2 data collection
- **Moralis Support**: Cross-chain transaction analysis
- **Zapper Integration**: DeFi protocol interaction tracking
- **Multi-Chain Aggregator**: Unified data from multiple blockchain networks

### 🎨 Modern Frontend
- **React + TypeScript**: Type-safe, modern web application
- **Axios Integration**: Robust API communication with interceptors
- **Real-time Updates**: Live credit score calculations and monitoring
- **Responsive Design**: Mobile-first, glass morphism UI design
- **Backend Health Monitoring**: Real-time backend status indicators

## 🏗️ Architecture

```
CVCCP/
├── 📁 backend/                 # Python FastAPI backend
│   ├── 🐍 api/                # API endpoints
│   ├── 🔌 clients/            # Blockchain data clients
│   ├── ⚙️ services/           # Business logic services
│   └── 🚀 start_api.py        # API server entry point
├── 📁 contracts/               # Solidity smart contracts
│   ├── 🔒 src/                # Contract source code
│   ├── 🧪 test/               # Contract tests
│   └── 📜 script/             # Deployment scripts
├── 📁 frontend/                # React TypeScript frontend
│   ├── 🎨 src/                # Source code
│   ├── 🧩 components/         # React components
│   ├── 🔌 services/           # API services
│   └── 📱 pages/              # Application pages
└── 📚 docs/                    # Documentation
```

## 🚀 Quick Start

### Prerequisites
- **Python 3.8+**
- **Node.js 18+**
- **Foundry** (for smart contract development)
- **Git**

### 1. Clone the Repository
```bash
git clone https://github.com/AryanG2311/CVCCP.git
cd CVCCP
```

### 2. Backend Setup
```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
python start_api.py
```

### 3. Smart Contract Setup
```bash
cd contracts
forge install
forge build
forge test
```

### 4. Frontend Setup
```bash
cd frontend
npm install
npm run dev
```

## 🔧 Configuration

### Backend Configuration
Create a `.env` file in the `backend/` directory:
```env
# API Configuration
API_HOST=0.0.0.0
API_PORT=8000
DEBUG=True

# Blockchain Configuration
ALCHEMY_API_KEY=your_alchemy_key
MORALIS_API_KEY=your_moralis_key
ZAPPER_API_KEY=your_zapper_key

# AI Configuration
GEMINI_API_KEY=your_gemini_key
```

### Frontend Configuration
The frontend automatically connects to `http://localhost:8000` for the backend API.

## 📊 API Endpoints

### Credit Score Calculation
```http
POST /api/calculate-score
Content-Type: application/json

{
  "address": "0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045",
  "force_refresh": false
}
```

### Response Format
```json
{
  "success": true,
  "address": "0xd8da6bf26964af9d7eed9e03e53415d37aa96045",
  "credit_score": {
    "totalScore": 335,
    "transactionScore": 35,
    "defiScore": 38,
    "stakingScore": 53,
    "riskScore": 160,
    "historyScore": 30,
    "confidence": 93,
    "lastUpdated": 1754909933,
    "updateCount": 5,
    "isActive": true
  },
  "ai_analysis": {
    "rating": "poor",
    "risk_level": "very_high",
    "score": 335,
    "recommendation": "declined",
    "summary": "AI analysis summary..."
  },
  "processing_time_seconds": 9.33,
  "rate_limited": true,
  "cache_used": true
}
```

## 🧪 Testing

### Backend Tests
```bash
cd backend
pytest
```

### Smart Contract Tests
```bash
cd contracts
forge test
```

### Frontend Tests
```bash
cd frontend
npm test
```

## 📈 Credit Scoring Algorithm

The CVCCP credit scoring system evaluates users based on multiple factors:

1. **Transaction Activity (25%)**: Volume and frequency of transactions
2. **DeFi Interactions (20%)**: Protocol usage and yield farming
3. **Staking Behavior (25%)**: Long-term commitment and staking patterns
4. **Risk Assessment (20%)**: Volatility and risk tolerance analysis
5. **Historical Patterns (10%)**: Consistency and reliability over time

**Final Score Range**: 300-850 (Higher is better)

## 🔒 Security Features

- **Smart Contract Audits**: Comprehensive security reviews
- **Access Control**: Role-based permissions and restrictions
- **Data Validation**: Input sanitization and verification
- **Rate Limiting**: API abuse prevention
- **Secure Communication**: HTTPS and encrypted data transmission

## 🌟 Key Technologies

### Backend
- **FastAPI**: High-performance Python web framework
- **Pydantic**: Data validation and settings management
- **SQLAlchemy**: Database ORM and management
- **Celery**: Asynchronous task processing

### Smart Contracts
- **Solidity 0.8+**: Modern smart contract language
- **Foundry**: Development and testing framework
- **OpenZeppelin**: Secure contract libraries

### Frontend
- **React 18**: Modern UI framework
- **TypeScript**: Type-safe development
- **Tailwind CSS**: Utility-first CSS framework
- **Axios**: HTTP client with interceptors
- **shadcn/ui**: High-quality UI components

### AI & Data
- **Gemini AI**: Advanced AI analysis
- **Alchemy**: Blockchain data provider
- **Moralis**: Cross-chain data aggregation
- **Zapper**: DeFi protocol tracking

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Workflow
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Scroll Protocol** for L2 infrastructure
- **Google Gemini AI** for advanced analysis capabilities
- **OpenZeppelin** for secure smart contract libraries
- **shadcn/ui** for beautiful UI components

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/AryanG2311/CVCCP/issues)
- **Discussions**: [GitHub Discussions](https://github.com/AryanG2311/CVCCP/discussions)
- **Documentation**: [API Integration Guide](CVCCP/frontend/API_INTEGRATION.md)

## 🔮 Roadmap

- [ ] **Q1 2025**: Multi-chain expansion (Polygon, Arbitrum)
- [ ] **Q2 2025**: Advanced AI models and predictions
- [ ] **Q3 2025**: Mobile application development
- [ ] **Q4 2025**: Institutional-grade features and compliance

---

**Built with ❤️ by the CVCCP Team**

*Empowering DeFi with intelligent credit scoring* 