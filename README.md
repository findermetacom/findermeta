# FINDERMETA - Crypto Token Trend Analyzer

FINDERMETA is a real-time cryptocurrency token analysis platform powered by DeepSeek AI. It monitors new token launches on pump.fun, analyzes their characteristics, and identifies emerging market trends.


## Features

### 1. Real-Time Token Monitoring
- Connects to pump.fun WebSocket API to receive new token launches
- Filters tokens by minimum market cap (default: 33 SOL)
- Reverses token data based on the frequency of words encountered. Processes token image to extract keywords
  — Transmits word frequency data based on new AI data for meta detection

### 2. Token Analysis
- Raw Data Column: Shows unprocessed token information as it arrives
- Analyzed Column: Displays filtered and processed tokens
- Current Meta Column: Shows current market trend analysis and top words

### 3. AI-Powered Trend Analysis
- Using DeepSeek artificial intelligence to analyze meta detection based on word frequency
- Identifies patterns and themes in successful tokens
- Generates meta-categories based on trending characteristics
- Updates trends every 60 seconds (configurable)

### 4. Word Frequency Analysis
- Tracks and displays top 20 most frequent words across all tokens
- Excludes common stopwords and URLs
- Color-codes words for better visualization
- Shows word frequency counts

### 5. Image Analysis
- Analyzes token images using AI vision model
- Extracts keywords and themes from images
- Integrates image analysis with text analysis

## Technical Architecture

### Frontend
- Pure JavaScript/HTML/CSS implementation
- Real-time updates via WebSocket
- Responsive design with mobile support
- Custom animations and transitions

### Backend
- Node.js server with Express
- MongoDB for data storage
- WebSocket server for real-time updates
- Integration with OpenAI API for text and vision analysis

### Key Components
1. WebSocket Handler: Manages real-time connections
2. Token Processor: Filters and analyzes incoming tokens
3. Word Frequency Tracker: Maintains word statistics
4. Image Analyzer: Processing of marker images by keyword decomposition
5. Meta Generator: Creates trend analysis using AI


## API Endpoints

### GET /api/getWordFrequencies
Returns top 20 most frequent words

### GET /api/getFiltredTokens
Returns processed tokens with frequency data

### GET /api/getMeta
Returns current meta analysis and related tokens

## WebSocket Events

### Client Events
- rawTokenLoaded: New unprocessed token
- tokenProcessed: Processed token data
- metaUpdate: New meta analysis
- globalWordUpdate: Word frequency updates
- topWordsUpdate: Top 20 words update

## Configuration

Environment variables:
- PORT: Server port (default: 3000)
- MONGODB_URI: MongoDB connection string
- DEBUG: Enable debug logging
- IMAGE_ANALYSE: Enable image analysis
- UPDATE_INTERVAL: Meta update interval (ms)
- MARKET_CAP_MIN: Minimum market cap     filter
- OPENAI_TEXT_API_KEY: Provider API key for text analysis
- OPENAI_TEXT_MODEL: Model name for text analysis
- OPENAI_TEXT_BASE_URL: Provider base URL for text analysis
- OPENAI_VISION_API_KEY: Provider API key for image analysis
- OPENAI_VISION_MODEL: Model name for image analysis
- OPENAI_VISION_BASE_URL: Provider base URL for image analysis



## Installation

1. Clone the repository
   git clone https://github.com/findermetacom/findermeta
   cd findermeta

2. Install dependencies
   npm install

3. Create .env file with required configuration
   cp .env.example .env
# Edit .env with your settings

4. Start MongoDB
# Make sure MongoDB is running

5. Start the server
   npm start

## Development

### Code Structure
- server.js: Main server implementation
- public/: Frontend files
    - index.html: Main page layout
    - styles.css: Styling
    - main.js: Frontend logic
- stopwords.json: Common words to filter out

### Adding New Features
1. Token Processing:
    - Extend processToken() in server.js
    - Update frontend display in main.js

2. AI Analysis:
    - Modify prompts in generateMetaToken()
    - Adjust image analysis in analyzeImage()

3. UI Components:
    - Add HTML elements to index.html
    - Style in styles.css
    - Add handlers in main.js

## License
MIT License

## Credits
https://x.com/findermetasol