# Research Tool for AI Environmental Impact - Design Guidelines

## Design Approach

**System Selected:** Material Design with academic research refinements
**Rationale:** Research tools require clarity, scanability, and information density. Material Design provides robust data table patterns, clear hierarchy, and proven interaction models for complex interfaces while maintaining accessibility.

## Core Design Elements

### Typography
- **Primary Font:** Inter or Roboto via Google Fonts CDN
- **Headings:** Bold (700) for page titles (text-3xl), Medium (500) for section headers (text-xl)
- **Body Text:** Regular (400) for content, Medium (500) for emphasis
- **Data/Metrics:** Mono font (JetBrains Mono) for numerical data, citations, and technical metrics
- **Reading Content:** max-w-prose containers for paper abstracts and descriptions

### Layout System
**Spacing Scale:** Tailwind units of 2, 4, 6, 8, 12, 16, 24
- Component padding: p-4 to p-8
- Section spacing: py-12 to py-24
- Card gaps: gap-6
- Dense data tables: p-2 to p-4

### Component Library

**Navigation:**
- Top navigation bar with search prominently featured
- Left sidebar for filtering (collapsible on mobile)
- Breadcrumb navigation for deep navigation paths

**Research Database Components:**
- **Paper Cards:** Elevated cards (shadow-md) with title, authors, publication date, citation count, and key metrics badge
- **Data Tables:** Sortable columns for model comparisons with sticky headers
- **Metric Pills:** Small badges showing kWh/token, CO2 emissions with color-coding for severity (no specific colors, but visual distinction)
- **Timeline Visualization:** Horizontal timeline showing research evolution with connected nodes
- **Citation Counter:** Prominent display of citation counts with link to source

**Search & Filters:**
- Prominent search bar (text-lg input with icon) at top of page
- Multi-select filter chips for: Model Type, Date Range, Impact Metric Type, Citation Threshold
- Active filters displayed as dismissible chips above results
- "Clear all filters" option

**Data Display:**
- **Model Comparison Table:** Sticky header table with columns: Model Name, Parameters, kWh per Token, CO2/Query, Last Updated, Source Citation
- **Research Paper List:** Card-based layout with metadata (authors, year, venue, citation count)
- **Metric Dashboard:** Grid of key statistics (grid-cols-2 md:grid-cols-4) showing aggregate data
- **Export Panel:** Download buttons for CSV, JSON, BibTeX formats

**Detail Views:**
- **Paper Detail Page:** Full abstract, methodology summary, extracted metrics, citation link, related papers
- **Model Detail Page:** Aggregated metrics from all sources, chart showing estimate evolution over time, confidence indicators

### Animations
Minimal - only subtle transitions on hover states and filter applications (transition-all duration-200)

## Images

**Hero Section:** No large hero image - this is a research tool prioritizing immediate access to data. Instead:
- Compact header (h-20) with tool name, tagline, and global search
- Direct transition to research content below

**Supporting Images:**
- Small institution/publisher logos within paper cards (h-8)
- Model vendor logos in comparison tables (h-6)
- Optional: Abstract visualization/chart thumbnails in paper previews (aspect-square, max 120px)

## Page Layouts

**Homepage/Dashboard:**
- Header with search (h-20)
- Stats overview section (4-column grid on desktop)
- "Recent Research" section with paper cards (3-column grid)
- "Top Cited Papers" section
- "Model Database" preview with table

**Search Results:**
- Left sidebar filters (w-64 on desktop, overlay on mobile)
- Main content area with search bar + active filters + results list
- Pagination at bottom

**Paper Detail:**
- Single column layout (max-w-4xl centered)
- Paper metadata card at top
- Tabbed interface: Abstract | Extracted Metrics | Citations | Related Papers

**Model Comparison:**
- Full-width sortable table
- Filter bar above table
- Chart section below showing trends

All pages maintain consistent header/footer with sticky navigation for seamless researcher workflow.