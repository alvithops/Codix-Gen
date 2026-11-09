# Product Requirements Document (PRD) - SustainAI Analyzer App

## 1. Product Overview

### 1.1 Product Name
**SustainAI Analyzer App**

### 1.2 Tagline
Analyzer App – AI Image Analyzer

### 1.3 Description
SustainAI is a modern web application built with Next.js that provides AI-powered solutions for sustainable development. The application aligns with UN Sustainable Development Goals (SDGs) and offers three main analyzer tools:
- CV Analysis (AI-Based CV Checker)
- Plant Disease Detection
- Waste Classification System

### 1.4 Target Audience
- Job seekers looking to optimize their CVs
- Farmers and agricultural workers needing plant disease diagnosis
- Waste management handlers and recycling enthusiasts
- Students and researchers interested in sustainability

### 1.5 Key Value Propositions
- AI-powered analysis for real-world problems
- Multi-language support (English & Indonesian)
- Responsive, modern UI built with latest web technologies
- Aligned with UN SDGs for global impact
- Client-server architecture keeping API keys secure

---

## 2. Stakeholders & Users

### 2.1 Primary Users
- **Job seekers**: Use CV Analyzer to improve resume quality
- **Farmers**: Use Plant Disease Detection to identify crop issues
- **Waste managers**: Use Waste Classification to sort recyclables
- **General users**: Explore sustainability solutions and learn about SDGs

### 2.2 Secondary Users
- **Developers/Technical**: Contribute to the codebase, deploy updates
- **Administrators**: Manage content, monitor analytics
- **Educators**: Use as teaching material for AI and sustainability

### 2.3 Organizational Stakeholders
- **UTDI Students**: Original developers (Hidayah, Fadil, Xavier)
- **Vercel Platform**: Hosting and deployment
- **Google AI Studio**: Gemini API for image analysis

---

## 3. Problem Statement

### 3.1 Core Problems Addressed
1. **Employment Barrier**: Millions lack access to decent work due to poorly optimized resumes
2. **Waste Crisis**: Inefficient sorting leads to recyclables in landfills, wasting economic potential
3. **Agricultural Loss**: Farmers lose crops to pests/diseases with limited early detection tools

### 3.2 Solution Approach
- AI-powered image and document analysis
- Instant feedback and recommendations
- User-friendly interface accessible to non-technical users
- Augmented intelligence (AI assists, humans make final decisions)

---

## 4. Goals & Success Metrics

### 4.1 Primary Goals
- [ ] Launch three functional analyzer tools (CV, Plant Disease, Waste)
- [ ] Achieve 90%+ user satisfaction with AI analysis quality
- [ ] Support both English and Indonesian languages
- [ ] Align all features with at least 3 UN SDGs each
- [ ] Deploy successfully on Vercel platform

### 4.2 Success Metrics
- **User Adoption**: Number of uploads/analyses per month
- **Quality**: AI analysis accuracy (measured via user feedback)
- **Accessibility**: Language switcher usage (% en vs % id)
- **Retention**: Return users after first analysis
- **SDG Alignment**: Number of SDG goals represented in features

### 4.3 Technical Targets
- **Performance**: Page load < 3 seconds on 3G
- **Availability**: 99% uptime on Vercel
- **Security**: API keys not exposed to clients
- **Responsiveness**: Mobile-first design, works on < 320px width

---

## 5. Features & Functionalities

### 5.1 Core Features

#### 5.1.1 CV Analyzer (AI-Based CV Checker)
- **Input**: Upload CV (PDF or image format)
- **Process**: AI analyzes CV against professional standards
- **Output**: 
  - Compatibility score (0-100)
  - Strengths and improvement areas
  - Skills identification
  - Formatting recommendations
  - ATS optimization tips
- **SDG Alignment**: 8 (Decent Work), 4 (Quality Education), 10 (Reduced Inequalities)

#### 5.1.2 Plant Disease Detection
- **Input**: Upload plant photo
- **Process**: AI identifies diseases and pests
- **Output**:
  - Disease identification
  - Severity assessment
  - Treatment recommendations
  - Prevention tips
- **SDG Alignment**: 2 (Zero Hunger), 1 (No Poverty), 15 (Life on Land)

#### 5.1.3 Waste Classification System
- **Input**: Upload waste image
- **Process**: AI classifies waste type
- **Output**:
  - Waste category (recyclable, organic, hazardous, etc.)
  - Recycling value assessment
  - Disposal recommendations
  - Waste bank integration info
- **SDG Alignment**: 12 (Responsible Consumption), 11 (Sustainable Cities), 13 (Climate Action)

### 5.2 User Interface Features
- **Language Switcher**: Toggle between English and Indonesian
- **Theme**: Light/dark mode support
- **Responsive Design**: Mobile-first, works on all screen sizes
- **Loading States**: Skeleton loaders and spinners
- **Error Handling**: User-friendly error messages
- **Copy to Clipboard**: Copy analysis results

### 5.3 Navigation & Structure
- **Navbar**: Fixed header with logo, nav links, language switcher
- **Hero Section**: Welcome message with call-to-action
- **Challenges Section**: Three global problems addressed
- **Solutions Section**: Feature showcase of three analyzers
- **How It Works**: 3-step workflow explanation
- **SDG Section**: UN Sustainable Development Goals alignment
- **Team Section**: Developer information
- **Footer**: Legal links, copyright, socials

### 5.4 API & Backend
- **AI Engine**: Google Gemini API (gemini-1.5-flash)
- **Endpoint**: `/api/analyze-cv`, `/api/analyze-plant`, `/api/analyze-waste`
- **Security**: API keys stored in `.env` (server-side only)
- **Request Flow**: 
  1. User uploads file → Frontend
  2. Frontend sends to backend API
  3. Backend adds hardcoded prompt → Gemini API
  4. Response parsed and displayed to user

---

## 6. Technical Requirements

### 6.1 Technology Stack
| Layer | Technology | Version |
|-------|-----------|---------|
| Framework | Next.js | 16.x |
| Language | TypeScript | 5.x |
| Styling | Tailwind CSS | 4.x |
| UI Components | Radix UI | Latest |
| Form Handling | React Hook Form | 7.x |
| Validation | Zod | 3.x |
| Charts | Recharts | 2.x |
| Animations | Tailwind CSS Animations | Latest |
| Icons | Lucide React | 0.454.0 |
| HTTP Client | Axios (inferred) | Latest |
| i18n | Custom Language Context | - |
| Deployment | Vercel | - |

### 6.2 Project Structure
```
SustainAi_Analyzer_App/
├── app/                          # Next.js App Router
│   ├── layout.tsx               # Root layout with providers
│   ├── page.tsx                 # Homepage composition
│   ├── globals.css              # Global styles
│   ├── api/                     # API routes
│   ├── CV-Analyzer/             # CV Analysis feature
│   ├── Plant-Disease-Analyzer/  # Plant Disease feature
│   ├── Waste-Analyzer/          # Waste Classification feature
│   ├── Privacy-Policy/          # Legal pages
│   └── Terms-of-Service/
├── components/                   # Reusable React components
│   ├── ui/                      # Base UI components (Radix UI)
│   ├── chat/                    # Chat interface components
│   ├── navbar.tsx               # Navigation
│   ├── hero-section.tsx         # Hero with canvas animations
│   ├── challenges-section.tsx   # Challenges presentation
│   ├── solutions-section.tsx    # Solutions showcase
│   ├── how-it-works-section.tsx # Feature explanation
│   ├── sdg-section.tsx          # SDG alignment
│   ├── team-section.tsx         # Team information
│   ├── cta-section.tsx          # Call-to-action
│   ├── footer.tsx               # Footer
│   ├── theme-provider.tsx       # Dark/Light theme
│   ├── language-switcher.tsx    # i18n switcher
│   ├── scroll-to-top-button.tsx # Scroll utility
│   └── navigation-progress.tsx  # Route loading indicator
├── hooks/                        # Custom React hooks
│   └── use-in-view.ts           # Intersection Observer hook
├── lib/                          # Utility functions & contexts
│   ├── language-context.tsx     # i18n context
│   ├── translations.ts          # Multi-language strings
│   └── utils.ts                 # Helper utilities
├── styles/                       # Global stylesheets
├── public/                       # Static assets
├── package.json                 # Dependencies & scripts
└── .env                         # Environment variables
```

### 6.3 API Routes
| Route | Method | Description |
|-------|--------|-------------|
| `GET /api/health` | Health check |
| `POST /api/analyze-cv` | Analyze CV document |
| `POST /api/analyze-plant` | Detect plant disease |
| `POST /api/analyze-waste` | Classify waste type |

### 6.4 Environment Variables
| Variable | Description | Required |
|----------|-------------|----------|
| `GEMINI_API_KEY_CV_ANALYZER` | Gemini API key for CV analysis | Yes |
| `GEMINI_API_KEY_PLANT_ANALYZER` | Gemini API key for plant analysis | Yes |
| `GEMINI_API_KEY_WASTE_ANALYZER` | Gemini API key for waste classification | Yes |
| `NEXT_PUBLIC_APP_URL` | Application URL | No (optional) |

### 6.5 Security Requirements
- API keys must NOT be exposed in client-side code
- All AI processing happens on server-side (API routes)
- Input validation on all uploads (file type, size limits)
- CORS configuration for production only
- Rate limiting on API endpoints
- Secure file storage (temporary, deleted after processing)

### 6.6 Performance Requirements
- **First Contentful Paint**: < 2.5s on broadband
- **Time to Interactive**: < 3.5s on broadband
- **Image Optimization**: Next.js Image component with proper sizing
- **Font Optimization**: next/font with Inter
- **Code Splitting**: Dynamic imports for heavy components
- **Caching**: Vercel ISR (Incremental Static Regeneration) where applicable

### 6.7 Accessibility Requirements
- WCAG 2.1 AA compliance minimum
- Keyboard navigable throughout
- Screen reader friendly labels
- Color contrast ratio > 4.5:1
- Focus visible states
- Language switcher accessible

---

## 7. User Stories

### 7.1 As a Job Seeker
- I want to upload my CV and get AI-powered analysis
- So I can improve my resume and get more job interviews
- **Acceptance Criteria**: Upload PDF/image, receive score 0-100, get specific feedback within 10 seconds

### 7.2 As a Farmer
- I want to upload a photo of my sick plant
- So I can identify the disease and get treatment
- **Acceptance Criteria**: Upload photo, get disease name, severity, treatment recommendations

### 7.3 As an Environment Enthusiast
- I want to classify waste types using AI
- So I can improve recycling and help the environment
- **Acceptance Criteria**: Upload photo, get waste category and recycling tips

### 7.4 As a Multilingual User
- I want to switch between English and Indonesian
- So I can use the app in my preferred language
- **Acceptance Criteria**: Language switcher persists in localStorage, all text translates

### 7.5 As a First-Time Visitor
- I want to understand the problem and solutions quickly
- So I can decide whether to use the app
- **Acceptance Criteria**: Hero section clear, challenges visible, CTA prominent

---

## 8. Non-Functional Requirements

### 8.1 Reliability
- 99% uptime on Vercel deployment
- Graceful error handling for API failures
- Fallback messages when AI service unavailable

### 8.2 Security
- API keys never in client bundle
- HTTPS enforcement
- No sensitive data stored long-term
- Input sanitization for all uploads

### 8.3 Maintainability
- Component-based architecture (as documented)
- Type-safe code (TypeScript 95.2%)
- Documented code patterns (ARCHITECTURE.md)
- Clear separation of concerns

### 8.4 Scalability
- Support concurrent users on Vercel
- Easy addition of new analyzer features
- Modular component structure for extensions

### 8.5 Compatibility
- Chrome, Firefox, Safari, Edge latest versions
- Mobile: iOS 14+, Android 10+
- Desktop: Windows 10+, macOS 10.15+

---

## 9. Roadmap & Milestones

### 9.1 Phase 1: MVP (Current State)
- [x] Three analyzer tools functional (CV, Plant, Waste)
- [x] Multi-language support (en/id)
- [x] Vercel deployment
- [x] Basic UI/UX
- [ ] User feedback collection

### 9.2 Phase 2: Enhancements
- [ ] User accounts & saved history
- [ ] PDF export of analysis results
- [ ] Improved AI prompt engineering
- [ ] Additional SDG alignments
- [ ] Analytics dashboard

### 9.3 Phase 3: Scale
- [ ] Payment integration (Stripe, credits system)
- [ ] Batch analysis capabilities
- [ ] API for third-party integration
- [ ] Mobile native app companion
- [ ] Enterprise features

### 9.4 Future Features (Post-MVP)
- Resume builder with template selection
- Plant care scheduling
- Community features (share results, compare)
- Advanced analytics and reporting
- Multi-language expansion (Spanish, French, etc.)

---

## 10. Dependencies Management

### 10.1 Production Dependencies
Key dependencies from package.json:
- `next@16.0.10` - React framework
- `react@19.2.0` & `react-dom@19.2.0` - UI library
- `@radix-ui/*` - UI components (17+ components)
- `zod@3.25.76` - Schema validation
- `react-hook-form@7.60.0` - Form management
- `recharts@2.15.4` - Data visualization
- `lucide-react@0.454.0` - Icon set
- `@vercel/analytics@1.3.1` - Usage analytics
- `tailwindcss-animate@1.0.7` - Animations

### 10.2 Development Dependencies
- `typescript@5` - Type safety
- `tailwindcss@4.1.9` - Styling
- `eslint` - Code linting
- `postcss` - CSS processing
- `tsx` - TypeScript execution

### 10.3 Package Manager
- `pnpm@10.28.2` - Preferred package manager
- Lockfile: `pnpm-lock.yaml` for reproducibility

---

## 11. Appendix

### 11.1 UN Sustainable Development Goals Alignment
| Feature | SDG 1 | SDG 2 | SDG 4 | SDG 8 | SDG 10 | SDG 11 | SDG 12 | SDG 13 | SDG 15 |
|---------|-------|-------|-------|-------|--------|--------|--------|--------|--------|
| CV Analyzer | | | ✓ | ✓ | ✓ | | | | |
| Plant Disease | ✓ | ✓ | | | | | | | ✓ |
| Waste Classification | | | | | | ✓ | ✓ | ✓ | |

### 11.2 Language Dictionary Structure (translations.ts)
```typescript
export const translations = {
  en: { /* English strings */ },
  id: { /* Indonesian strings */ }
}
```

### 11.3 AI Prompt Engineering Pattern
- Hardcoded prompts on server-side
- Language-specific prompts (EN/ID)
- JSON-only response format
- No markdown, no backticks, no explanations

### 11.4 Technical Decisions Rationale
- **Next.js 16 + App Router**: Latest features, optimal performance
- **TypeScript 95.2%**: Type safety, better developer experience
- **Tailwind CSS 4**: Utility-first, rapid UI development
- **Radix UI**: Accessible primitives, unopinionated styling
- **Server-side AI**: Security of API keys
- **Vercel Deployment**: Easy deployment, built-in analytics, edge functions

---
*PRD generated based on analysis of GitHub repository christianxavierVibecode/SustainAi_Analyzer_App*