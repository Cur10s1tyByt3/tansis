# Tansis AI

A modern web application for transliterating Arabic text to Latin script using various academic transliteration standards. Built with Next.js 15 and powered by OpenAI.

## Features

- **Multiple Transliteration Standards**: Support for IJMES, ALA-LC, DIN 31635, Buckwalter, Custom, and SHARIAsource styles
- **Bidirectional Conversion**: Convert Arabic to Latin script and reverse transliteration
- **Batch Processing**: API endpoint for processing multiple texts at once
- **Responsive Design**: Optimized for both desktop and mobile devices
- **Real-time Processing**: Instant transliteration with loading states
- **Error Handling**: Comprehensive error handling with retry logic for SHARIAsource

## Supported Transliteration Standards

- **IJMES** - International Journal of Middle Eastern Studies standard
- **ALA-LC** - American Library Association - Library of Congress romanization
- **DIN 31635** - German transliteration standard
- **Buckwalter** - ASCII-only transliteration system
- **SHARIAsource** - Enhanced IJMES with specific scholarly conventions
- **Custom** - Simplified, readable romanization

## Tech Stack

- **Framework**: Next.js 15 with App Router
- **Frontend**: React 19, TypeScript, Tailwind CSS
- **UI Components**: Radix UI primitives with custom styling
- **AI Integration**: OpenAI GPT-4
- **Styling**: Tailwind CSS with custom design system
- **Forms**: React Hook Form with Zod validation

## Getting Started

### Prerequisites

- Node.js 18+ 
- npm, yarn, pnpm, or bun
- OpenAI API key and endpoint

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd t-2
```

2. Install dependencies:
```bash
npm install
# or
yarn install
# or
pnpm install
# or
bun install
```

3. Set up environment variables:
Create a `.env.local` file in the root directory with:
```env
AZURE_OPENAI_API_KEY=your_api_key_here
AZURE_OPENAI_ENDPOINT=your_endpoint_here
AZURE_4_1_DEPLOYMENT=your_deployment_name
```

4. Run the development server:
```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

5. Open [http://localhost:3000](http://localhost:3000) in your browser.

## API Endpoints

### Single Transliteration
```
POST /api/transliterate
```

**Request Body:**
```json
{
  "text": "السلام عليكم",
  "style": "IJMES",
  "reverse": false
}
```

**Response:**
```json
{
  "transliteration": "al-salām ʿalaykum"
}
```

### Batch Transliteration
```
POST /api/transliterate/batch
```

**Request Body:**
```json
{
  "texts": ["السلام عليكم", "مرحبا"],
  "style": "IJMES",
  "reverse": false
}
```

**Response:**
```json
{
  "results": [
    {
      "text": "السلام عليكم",
      "transliteration": "al-salām ʿalaykum"
    },
    {
      "text": "مرحبا", 
      "transliteration": "marḥaban"
    }
  ]
}
```

### API Documentation
```
GET /api/transliterate
```

Returns comprehensive API documentation with available styles and examples.

## Project Structure

```
├── app/                    # Next.js App Router
│   ├── api/               # API routes
│   │   └── transliterate/ # Transliteration endpoints
│   ├── globals.css        # Global styles
│   ├── layout.tsx         # Root layout
│   └── page.tsx           # Home page
├── components/            # React components
│   ├── ui/               # Reusable UI components
│   └── *.tsx             # Feature components
├── lib/                  # Utility libraries
│   ├── openai.ts         # Azure OpenAI configuration
│   ├── styles.ts         # Transliteration styles & prompts
│   └── utils.ts          # Helper utilities
├── types/                # TypeScript type definitions
├── playground/           # Development scripts and test data
└── scripts/              # Build and utility scripts
```

## Development

### Available Scripts

- `npm run dev` - Start development server with Turbopack
- `npm run build` - Build production application
- `npm run start` - Start production server
- `npm run lint` - Run ESLint

### Testing

Use the playground scripts to test the API:

```bash
node playground/test_api.js
```

## Contributing

1. Follow the existing code style and conventions
2. Use TypeScript for all new code
3. Add appropriate error handling
4. Update documentation for new features
5. Test thoroughly before submitting

## License

This project is private and not open for public distribution.

## Support

For issues and questions, please refer to the project documentation or contact the development team.