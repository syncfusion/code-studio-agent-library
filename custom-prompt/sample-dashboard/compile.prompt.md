---
name: compile
agent: agent
description: Compile specification to production code
---
# Compile Dashboard Specification to Code

## Task
Convert the specification in `dashboard.prompt.md` to working React/TypeScript code.

## Steps

### 1. Read Specification
- Read `dashboard.prompt.md` completely
- Understand all features, components, and requirements
- Note mock data structure and API design

### 2. Create Project Structure
- Ensure all folders exist in `src/` directory
- Create necessary subdirectories: components, services, types, hooks, utils, data, styles

### 3. Generate Core Types
Create `src/types/` files:
- `dashboard.types.ts` - Dashboard interfaces
- `metrics.types.ts` - Metric data types
- `widget.types.ts` - Widget configuration types

### 4. Generate Mock Data
Create `src/data/mockData.ts`:
- Generate mock metric data for all KPIs
- Create time-series data for charts
- Include data for all segments and regions
- Add realistic values with trends

### 5. Create Utility Functions
Create `src/utils/` files:
- `formatters.ts` - Format values, currencies, percentages
- `generators.ts` - Generate random data for polling simulation
- `calculations.ts` - Calculate trends, percentages, aggregations

### 6. Create Custom Hooks
Create `src/hooks/` files:
- `usePolling.ts` - Handle polling for metric updates
- `useDashboard.ts` - Manage dashboard state
- `useLocalStorage.ts` - Persist layout to localStorage

### 7. Create Services
Create `src/services/` files:
- `dashboardService.ts` - Dashboard operations
- `dataService.ts` - Fetch mock data with delays
- `exportService.ts` - PDF and CSV export functionality

### 8. Create UI Components
Create `src/components/` files:
- `MetricWidget.tsx` - Display KPI with trend
- `ChartWidget.tsx` - Render chart (line/bar/pie)
- `LayoutGrid.tsx` - Responsive grid layout
- `FilterPanel.tsx` - Time range and segmentation filters
- `Header.tsx` - Top navigation
- `Sidebar.tsx` - Left navigation
- `Dashboard.tsx` - Main dashboard orchestrator

### 9. Create Main App Files
- `App.tsx` - Root component with routing/layout
- `main.tsx` - React entry point
- `styles/globals.css` - Tailwind + global styles

### 10. Build & Test
- Run `npm run build`
- Check for TypeScript errors
- Verify no console warnings
- Test all components render correctly

## Code Quality Guidelines
- Use TypeScript strict mode (no `any` types)
- Components should be reusable and well-composed
- Use descriptive variable names
- Add comments for complex logic
- Keep functions under 50 lines
- Implement proper error handling

## Expected Output
- All files created without errors
- Dashboard loads and displays mock data
- Widgets update on filter change
- Layout persists across reloads
- Export functionality available
- Fully responsive design
- Ready for further customization

## Success Criteria
- ✓ No TypeScript compilation errors
- ✓ No console errors on load
- ✓ All components visible and interactive
- ✓ Responsive on mobile/tablet/desktop
- ✓ Metrics display with trends
- ✓ Charts render correctly
- ✓ Filtering works properly