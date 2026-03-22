# Gemini API Integration

This project now includes integration with the Gemini API for enhanced financial services including currency rates, conversion, and AI-powered financial advice.

## Setup Instructions

1. **Get a Gemini API Key**:
   - Visit [Google AI Studio](https://makersuite.google.com/app/apikey) to generate an API key
   - Note: The free tier allows for generous usage limits

2. **Configure Environment Variables**:
   - Update the `.env.local` file with your actual Gemini API key:
   ```
   GEMINI_API_KEY=your_actual_gemini_api_key_here
   NEXT_PUBLIC_GEMINI_API_KEY=your_actual_gemini_api_key_here
   ```
   - Replace `your_actual_gemini_api_key_here` with your real API key
   - The API key should be at least 30 characters long

3. **Restart the Development Server**:
   - After updating the API key, restart the development server for changes to take effect

## Features Powered by Gemini

### 1. Currency Rates
- Enhanced currency rate fetching with AI analysis
- Fallback to traditional APIs with Gemini-enhanced data interpretation

### 2. Currency Conversion
- Smart currency conversion with real-time rates
- AI-powered insights on conversion trends

### 3. AI Financial Advisor
- Conversational AI financial advisor using Gemini Pro
- Professional financial advice on currency exchange, investments, and market trends

### 4. Market Analysis
- AI-generated market analysis reports
- Trend predictions and risk assessments

## API Functions

The integration includes several utility functions in `lib/gemini.ts`:

- `fetchCurrencyRates()` - Fetches currency exchange rates
- `convertCurrency()` - Converts between currencies
- `getFinancialAdvice()` - Provides AI-powered financial advice
- `getHistoricalData()` - Retrieves historical currency data
- `generateMarketAnalysis()` - Creates market analysis reports
- `isGeminiAvailable()` - Checks if Gemini is properly configured
- `getGeminiUnavailableReason()` - Gets the reason why Gemini is not available

## Components Using Gemini

1. **Home Page** (`app/page.tsx`) - Uses Gemini for currency rates display
2. **Converter Page** (`app/converter/page.tsx`) - Uses Gemini for currency conversion
3. **Advisor Page** (`app/advisor/page.tsx`) - Uses Gemini for AI chat responses

## Error Handling

All Gemini API calls include proper error handling with fallbacks to traditional APIs to ensure reliability. The application gracefully degrades when the API key is not configured:

- If Gemini is not configured, the advisor provides general financial advice
- All components continue to function with fallback mechanisms
- Clear error messages are displayed when issues occur

## Troubleshooting

### Common Issues and Solutions

1. **Chat not responding**:
   - Check that your Gemini API key is correctly set in `.env.local`
   - Verify the API key has not expired
   - Ensure you have internet connectivity
   - The API key should be at least 30 characters long

2. **"Gemini not configured" message**:
   - Confirm both `GEMINI_API_KEY` and `NEXT_PUBLIC_GEMINI_API_KEY` are set
   - Make sure the API key is not set to the placeholder value
   - Restart the development server after updating environment variables

3. **Rate limiting**:
   - The free tier has usage limits; monitor your usage in the Google AI Studio console
   - Implement request throttling if needed for high-traffic applications

## Future Enhancements

- Real-time market sentiment analysis
- Personalized investment recommendations
- Advanced risk assessment models
- Automated portfolio rebalancing suggestions