# ESG & Climate Risk Analytics Accelerator

Enterprise-grade ESG and climate risk analytics with carbon modeling, stress testing, regulatory compliance monitoring, and ML-powered default predictions — built as a Snowflake Native App.

## Features

### Executive Dashboard
- Portfolio-level ESG summary with weighted scores
- Carbon intensity and climate exposure metrics
- Sector climate risk overview with interactive charts
- Green vs Brown asset allocation tracking

### Carbon Analytics
- Scope 1/2/3 emissions tracking and trends
- Carbon intensity benchmarking by sector
- Renewable energy adoption monitoring
- Top emitters identification and YoY analysis

### ESG Ratings & Scores
- Multi-agency ESG rating band distribution
- Environmental, Social, Governance pillar breakdown
- Controversy tracking and sector comparison
- Rating migration analysis

### Climate Stress Testing
- Fed/NGFS scenario-based portfolio stress testing
- Transition vs Physical risk decomposition
- Stranded asset exposure analysis
- Portfolio loss by temperature pathway

### Portfolio Exposure
- Climate & ESG exposure by sector and asset class
- Climate VaR contribution analysis
- Portfolio weight distribution
- Top climate-risk holdings identification

### Regulatory Compliance
- SEC Climate Disclosure tracking
- EPA GHG Reporting (40 CFR Part 98)
- Dodd-Frank, SOX 404, CFTC compliance
- Upcoming deadline alerts for non-compliant entities

### ML Default Predictions
- Ridge Regression carbon intensity forecasting
- Climate-adjusted default probability scoring
- Monte Carlo portfolio Climate VaR estimation
- Risk tier classification (Low/Moderate/High/Critical)

## Required Data Tables

After installing, bind these 10 table references:

| Reference | Key Columns |
|-----------|-------------|
| Companies | COMPANY_ID, COMPANY_NAME, SECTOR, REGION, MARKET_CAP_USD, REVENUE_USD |
| Carbon Metrics | COMPANY_ID, REPORT_YEAR, SCOPE_1/2/3, TOTAL_EMISSIONS, CARBON_INTENSITY, RENEWABLE_PCT |
| ESG Ratings | COMPANY_ID, OVERALL_ESG_SCORE, ENV/SOCIAL/GOV scores, ESG_RATING_BAND, CONTROVERSY_COUNT |
| Portfolio Exposure | PORTFOLIO_ID, COMPANY_NAME, SECTOR, MARKET_VALUE_USD, WEIGHT_PCT, CLIMATE_VAR_PCT |
| Climate Stress Scenarios | SCENARIO_NAME, TEMP_PATHWAY_C, AVG/MAX_PORTFOLIO_LOSS, STRANDED_ASSET_PCT |
| Climate Stress Results | PORTFOLIO_ID, SCENARIO_NAME, PORTFOLIO_LOSS_PCT, CARBON_COST_IMPACT |
| Portfolio ESG Summary | PORTFOLIO_ID, TOTAL_AUM_USD, WEIGHTED_ESG_SCORE, CLIMATE_EXPOSURE_PCT |
| Sector Climate Risk | SECTOR, REPORT_YEAR, AVG_CARBON_INTENSITY, TRANSITION/PHYSICAL_RISK_SCORE |
| Regulatory Compliance | COMPANY_ID, REGULATION, COMPLIANCE_STATUS, NEXT_DEADLINE, CRITICAL_FINDINGS |
| Regulatory Dashboard | REGULATION, COMPLIANCE_RATE_PCT, COMPLIANT/PARTIAL/NON_COMPLIANT_COUNT |

## Permissions

The app requests SELECT access on bound tables. All analytics run in-place on your Snowflake warehouse. No data leaves your account.

## Architecture

Medallion architecture: Bronze (raw) > Silver (enriched) > Gold (aggregated)

## Version History

| Version | Date | Notes |
|---------|------|-------|
| 1.0.0 | 2026-05-14 | Initial marketplace release |
