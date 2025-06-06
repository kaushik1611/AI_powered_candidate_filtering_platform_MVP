
![screencapture-onecompiler-html-43kxqwsh4-2025-06-06-15_38_24](https://github.com/user-attachments/assets/98f57cc9-6ac4-409a-8b98-a4289dcb1e71)


# AI Candidate Assessment Platform

> A comprehensive AI-powered candidate filtering and assessment platform for executive recruitment, built with Material Design principles and mobile-first responsive architecture.

## 🚀 Overview

The AI Candidate Assessment Platform automates the evaluation of candidates for executive positions using GPT-4 and structured scoring logic. This lean MVP provides recruiters with intelligent candidate analysis, comprehensive scoring, and professional reporting capabilities.

## ✨ Features

### 🎯 Core Functionality
- **AI-Powered Assessment** - GPT-4 integration for intelligent candidate evaluation
- **Multi-Document Upload** - Support for role profiles, company info, CVs, and transcripts
- **Structured Scoring** - Comprehensive evaluation across multiple criteria
- **Real-time Processing** - Live progress tracking during AI analysis
- **Professional Reporting** - Detailed results with strengths/weaknesses analysis
- **Assessment History** - Complete audit trail of all evaluations

### 📱 Mobile-First Design
- **Responsive Layout** - Optimized for all devices (320px to 1920px+)
- **Material Design** - Google's design system for consistent UX
- **Touch Optimized** - 48dp minimum touch targets, gesture support
- **Progressive Enhancement** - Works on all modern browsers
- **Offline Ready** - Local storage and graceful degradation

### 🎨 User Experience
- **Intuitive Interface** - Clean, professional Material Design
- **Drag & Drop Upload** - Easy file management
- **Real-time Validation** - Instant feedback on form completion
- **Smooth Animations** - Material Design motion principles
- **Accessible Design** - WCAG AA compliant

## 🛠 Tech Stack

### Frontend
- **HTML5** - Semantic markup structure
- **CSS3** - Material Design implementation with CSS Grid/Flexbox
- **Vanilla JavaScript** - No framework dependencies
- **Material Icons** - Google's icon library
- **Roboto Font** - Material Design typography

### Recommended Backend (Not Included)
- **FastAPI** (Python) or **Express.js** (Node.js)
- **OpenAI GPT-4 API** - AI assessment engine
- **Whisper API** - Speech-to-text for audio transcripts
- **Supabase** or **Firebase** - Database and authentication
- **AWS S3** or **Vercel Blob** - File storage

### Deployment
- **Vercel** - Frontend hosting (recommended)
- **Render** or **Railway** - Backend hosting
- **CloudFlare** - CDN and performance optimization

## 📋 File Upload Support

| Document Type | Supported Formats | Max Size | Required |
|---------------|------------------|----------|----------|
| Role Profile | PDF, DOC, DOCX | 10MB | ✅ Yes |
| Company Info | PDF, DOC, DOCX | 10MB | No |
| Scoring Template | PDF, DOC, XLS, XLSX | 10MB | No |
| Candidate CV | PDF | 10MB | ✅ Yes |
| Interview Transcript | TXT, PDF, MP3, WAV | 25MB | ✅ Yes* |
| Manual Transcript | Text Input | - | ✅ Yes* |

*Either interview file or manual transcript required

## 🎯 Assessment Criteria

The platform evaluates candidates across six key dimensions:

1. **Technical Skills** (0-100)
2. **Leadership** (0-100)
3. **Communication** (0-100)
4. **Problem Solving** (0-100)
5. **Cultural Fit** (0-100)
6. **Experience** (0-100)

### Scoring System
- **80-100**: Highly Recommended
- **70-79**: Recommended
- **Below 70**: Consider

## 📱 Responsive Breakpoints

| Breakpoint | Range | Layout | Features |
|------------|-------|--------|----------|
| Mobile Portrait | 320px - 480px | 1 column | Compact stats, stacked uploads |
| Mobile Landscape | 481px - 768px | 2 columns | Balanced layout, hidden nav |
| Tablet | 769px - 1024px | 2-3 columns | Partial navigation, optimized grid |
| Desktop | 1025px+ | 3+ columns | Full navigation, all features |

## 🚀 Quick Start

### 1. Clone/Download
```bash
# Download the HTML file or clone repository
wget https://example.com/ai-candidate-platform.html
```

### 2. Local Development
```bash
# Open with any local server
python -m http.server 8000
# or
npx serve .
# or simply open in browser
open ai-candidate-platform.html
```

### 3. Deploy to Vercel
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel

# Or drag & drop to vercel.com
```

## 🔧 Customization

### Branding
```css
:root {
    --primary: #1976d2;        /* Primary color */
    --secondary: #388e3c;      /* Secondary color */
    --accent: #ff5722;         /* Accent color */
}
```

### API Integration Points
```javascript
// File upload endpoint
const uploadEndpoint = '/api/upload';

// AI processing endpoint
const assessmentEndpoint = '/api/assess';

// Results retrieval
const resultsEndpoint = '/api/results/{id}';
```

### Environment Variables
```env
OPENAI_API_KEY=your_openai_api_key
WHISPER_API_KEY=your_whisper_api_key
DATABASE_URL=your_database_url
STORAGE_BUCKET=your_storage_bucket
```

## 🔗 Backend Integration

### Required API Endpoints

#### POST /api/upload
Upload and validate documents
```json
{
    "file": "base64_encoded_file",
    "type": "cv|profile|transcript",
    "candidateId": "uuid"
}
```

#### POST /api/assess
Process AI assessment
```json
{
    "candidateId": "uuid",
    "documents": ["doc1", "doc2"],
    "scoringCriteria": "template"
}
```

#### GET /api/results/{id}
Retrieve assessment results
```json
{
    "candidateId": "uuid",
    "overallScore": 85,
    "scores": {...},
    "analysis": "AI generated analysis",
    "recommendation": "Highly Recommended"
}
```

## 📊 Analytics & Metrics

### Key Performance Indicators
- **Assessment Completion Rate** - % of started assessments completed
- **Average Processing Time** - Time from upload to results
- **Score Distribution** - Distribution of candidate scores
- **User Engagement** - Session duration and page interactions

### Tracking Implementation
```javascript
// Google Analytics 4 (recommended)
gtag('event', 'assessment_started', {
    'candidate_name': candidateName,
    'assessment_type': 'executive'
});

// Custom analytics
analytics.track('Assessment Completed', {
    score: overallScore,
    recommendation: recommendation,
    processingTime: duration
});
```

## 🔒 Security Considerations

### Data Protection
- **File Validation** - Strict file type and size validation
- **Sanitization** - Input sanitization for all user data
- **Encryption** - TLS 1.3 for data in transit
- **Access Control** - Role-based permissions
- **Audit Logging** - Complete action audit trail

### Privacy Compliance
- **GDPR Ready** - Data protection and right to deletion
- **Data Retention** - Configurable retention policies
- **Anonymization** - Personal data anonymization options
- **Consent Management** - Clear consent workflows

## 🧪 Testing

### Browser Compatibility
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ✅ Mobile Safari (iOS 12+)
- ✅ Chrome Mobile (Android 8+)

### Performance Targets
- **First Contentful Paint**: < 1.5s
- **Largest Contentful Paint**: < 2.5s
- **Cumulative Layout Shift**: < 0.1
- **Time to Interactive**: < 3s

### Accessibility
- **WCAG 2.1 AA** compliance
- **Screen reader** compatibility
- **Keyboard navigation** support
- **High contrast** mode support

## 📈 Roadmap

### Phase 1 (Current)
- ✅ Core assessment functionality
- ✅ Material Design UI
- ✅ Mobile responsiveness
- ✅ File upload system

### Phase 2 (Planned)
- 🔄 Backend API integration
- 🔄 User authentication
- 🔄 Advanced analytics dashboard
- 🔄 PDF export functionality

### Phase 3 (Future)
- 📅 Bulk candidate processing
- 📅 Custom scoring templates
- 📅 Integration with ATS systems
- 📅 Advanced AI models (GPT-5)

## 🤝 Contributing

### Development Setup
```bash
# Clone repository
git clone https://github.com/yourorg/ai-candidate-platform

# Install dependencies (if applicable)
npm install

# Start development server
npm run dev
```

### Code Standards
- **HTML**: Semantic markup, accessibility attributes
- **CSS**: BEM methodology, Material Design principles
- **JavaScript**: ES6+, JSDoc comments, error handling

### Pull Request Process
1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

### Documentation
- **API Documentation**: `/docs/api`
- **User Guide**: `/docs/user-guide`
- **Developer Guide**: `/docs/developer-guide`

### Contact
- **Email**: support@yourcompany.com
- **Slack**: #ai-platform-support
- **GitHub Issues**: [Create Issue](https://github.com/yourorg/ai-candidate-platform/issues)

### FAQ

**Q: Can I customize the scoring criteria?**
A: Yes, the scoring template upload allows for custom evaluation criteria.

**Q: What file formats are supported for CVs?**
A: Currently PDF format only. Additional formats can be added in backend implementation.

**Q: Is there a limit on assessment history?**
A: The frontend displays the 5 most recent assessments. Full history is available through backend API.

**Q: Can multiple users access the same assessment?**
A: Yes, with proper backend authentication and authorization implementation.

---

**Built with ❤️ for executive recruitment professionals**

*Last updated: June 2025*
