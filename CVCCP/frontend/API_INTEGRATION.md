# API Integration Documentation

## Overview
The frontend now integrates with the real credit score calculation API endpoint at `http://localhost:8000/api/calculate-score`.

## API Endpoint
- **URL**: `http://localhost:8000/api/calculate-score`
- **Method**: POST
- **Content-Type**: `application/json`

## Request Format
```json
{
  "address": "0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045",
  "force_refresh": false
}
```

### Parameters
- `address` (string): Ethereum wallet address to analyze
- `force_refresh` (boolean): Whether to bypass cache and force a fresh calculation

## Response Format
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
  "contract_transactions": {},
  "processing_time_seconds": 9.33,
  "ai_analysis": {
    "rating": "poor",
    "risk_level": "very_high",
    "score": 335,
    "recommendation": "declined",
    "summary": "This DeFi credit profile presents a highly risky lending prospect..."
  },
  "rate_limited": true,
  "cache_used": true,
  "error": null,
  "timestamp": "2025-08-11T16:30:26.824762"
}
```

## New Components

### 1. AIAnalysisCard
Displays AI analysis results including:
- Rating (excellent, good, fair, poor)
- Risk level (very_low, low, medium, high, very_high)
- Recommendation (approved, declined, pending)
- Summary text
- AI score

### 2. MetadataCard
Shows processing details:
- Processing time
- Cache usage status
- Rate limiting status
- Update count
- Last updated timestamp
- Active status

### 3. Updated ScoreCard
Enhanced to handle:
- Optional weight display
- Optional percentage/progress bar
- Flexible max score values

## Features

### Address Validation
- Real-time validation of Ethereum addresses
- Visual feedback for invalid addresses

### Force Refresh Option
- Checkbox to bypass cache and force fresh calculation
- Useful for getting updated scores

### Error Handling
- Comprehensive error display
- User-friendly error messages
- Graceful fallbacks

### Real-time Updates
- Live processing status
- Dynamic score updates
- Responsive UI with animations

## Usage

1. Enter a valid Ethereum wallet address
2. Optionally check "Force refresh" to bypass cache
3. Click "Analyze Credit Score"
4. View comprehensive results including:
   - Main credit score with circular progress
   - Individual component scores
   - AI analysis and recommendations
   - Processing metadata
   - Blockchain explorer links

## Technical Details

### State Management
- Uses React hooks for state management
- Proper error handling and loading states
- TypeScript interfaces for type safety

### API Service
- **Axios Integration**: Uses axios instead of native fetch for better error handling and features
- **Request/Response Interceptors**: Automatic logging of all API calls and responses
- **Timeout Configuration**: 30-second timeout for API requests
- **Error Handling**: Comprehensive error handling with specific error messages for different failure scenarios
- **Health Checks**: Built-in methods to check backend availability and status
- **Centralized Configuration**: Single axios instance with consistent settings

### UI Components
- Built with shadcn/ui components
- Responsive design with Tailwind CSS
- Smooth animations and transitions
- Glass morphism design elements

## Backend Requirements

The backend must be running on `http://localhost:8000` and provide the `/api/calculate-score` endpoint with the specified request/response format.

## Development

To run the frontend:
```bash
cd CVCCP/frontend
npm install
npm run dev
```

To build for production:
```bash
npm run build
```

## Axios Features

### Request/Response Interceptors
- **Request Logging**: All API requests are logged with method, URL, and data
- **Response Logging**: All API responses are logged with status and data
- **Error Logging**: Comprehensive error logging for debugging

### Error Handling
- **Network Errors**: Specific handling for connection issues
- **Server Errors**: Detailed error messages with status codes
- **Timeout Handling**: 30-second timeout with user-friendly messages
- **Fallback Messages**: Graceful error messages for different failure scenarios

### Additional Methods
- `checkBackendHealth()`: Check if backend is responding
- `getBackendStatus()`: Get detailed backend status information

### Configuration
- **Base URL**: Configurable API endpoint
- **Timeout**: 30-second request timeout
- **Headers**: Automatic Content-Type application/json
- **Interceptors**: Built-in logging and error handling

## Examples

See `src/examples/apiUsage.ts` for comprehensive usage examples including:
- Basic credit score calculation
- Backend health monitoring
- Batch address processing
- Retry logic with exponential backoff
- Error handling patterns 