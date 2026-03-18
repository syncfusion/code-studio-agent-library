---
name: test-workflow
agent: agent
description: Generate tests from specification
---
# Generate Tests from Specification

## Task
Create comprehensive tests matching the dashboard specification in `dashboard.prompt.md`

## Test Structure

### Unit Tests (`tests/unit/`)

#### Formatter Tests
```
test_formatCurrency_withUSD_returnsFormattedValue
test_formatPercentage_withPositive_returnsGreenColor
test_formatPercentage_withNegative_returnsRedColor
test_formatNumber_withThousands_addsCommas
```

#### Hook Tests
```
test_usePolling_startsOnMount
test_usePolling_callsCallbackAtInterval
test_usePolling_cleansUpOnUnmount
test_useLocalStorage_persistsData
test_useLocalStorage_retrievesPersistedData
test_useDashboard_initializesWithDefaultState
test_useDashboard_updateFilters_refreshesData
```

#### Component Tests
```
test_MetricWidget_renders_metricName
test_MetricWidget_displays_currentValue
test_MetricWidget_shows_trendPercentage
test_MetricWidget_colorChange_onPositiveTrend
test_MetricWidget_showsRetry_onError
test_ChartWidget_renders_rechartComponent
test_ChartWidget_updatesData_onPropsChange
test_LayoutGrid_renders_children
test_LayoutGrid_accepts_dragEvents
test_FilterPanel_renders_allFilters
test_FilterPanel_emits_filterChange_onSelection
```

### Integration Tests (`tests/integration/`)

#### Dashboard Integration
```
test_Dashboard_loadsInitialData
test_Dashboard_displaysMetricsAndCharts
test_Dashboard_filterChange_updatesAllWidgets
test_Dashboard_layoutPersists_onReload
test_Dashboard_addWidget_addsToGrid
test_Dashboard_removeWidget_removesFromGrid
```

#### Data Service Integration
```
test_dataService_fetchMetrics_returnsData
test_dataService_fetchChartData_returnsArray
test_dataService_supportsTimeRangeFilter
test_dataService_supportsRegionFilter
test_dataService_supportsSegmentFilter
```

#### Export Service Integration
```
test_exportService_generatePDF_creates_file
test_exportService_exportCSV_creates_file
test_exportService_export_includesHeaders
test_exportService_export_includesTimestamp
```

### E2E Tests (`tests/e2e/`)

#### User Workflows
```
test_userFlow_viewDashboard_seesMetrics
test_userFlow_filterByTimeRange_updatesCharts
test_userFlow_dragWidget_reordersLayout
test_userFlow_exportDashboard_downloadsPDF
test_userFlow_exportData_downloadsCSV
test_userFlow_customLayout_persistsAfterRefresh
test_userFlow_multipleFilters_appliesCorrectly
```

## Test Coverage Requirements

For each feature in spec:
1. **Happy path test** (valid inputs, success case)
2. **Error path test** (invalid inputs, error handling)
3. **Edge case test** (boundary conditions, null values)
4. **Performance test** (meets spec latency requirements)

### Coverage Targets
- Utilities: 100% coverage
- Hooks: 95%+ coverage
- Components: 85%+ coverage
- Services: 90%+ coverage
- **Overall: 80%+ coverage**

## Test Naming Convention
Format: `test_[component/service]_[action]_[expected]`

Examples:
```
test_metricWidget_displayValue_formatsWithCommas
test_layoutGrid_onDrop_reordersWidgets
test_dataService_fetch_returnsData_within1Second
test_filterPanel_selectTimeRange_emitsChange
```

## Testing Stack
- Framework: Jest
- Component testing: React Testing Library
- Assertions: Jest matchers
- Mocking: Jest mocks and spies

## Test File Organization
```
tests/
├── unit/
│   ├── formatters.test.ts
│   ├── hooks.test.ts
│   ├── components.test.tsx
│   └── calculations.test.ts
├── integration/
│   ├── dashboard.test.tsx
│   ├── dataService.test.ts
│   └── exportService.test.ts
└── e2e/
    └── userFlows.test.tsx
```

## Running Tests
```bash
# Run all tests
npm run test

# Run with coverage
npm run test:coverage

# Run specific test file
npm run test -- formatters.test.ts

# Watch mode
npm run test:watch
```

## Success Criteria
-  All acceptance criteria have tests
-  Test coverage > 80%
-  All tests pass
-  Tests run in < 10 seconds
-  No test warnings
-  Tests are maintainable and clear
