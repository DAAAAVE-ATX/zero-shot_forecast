## Laboratory 1

Project: Healthcare Zero-Shot Forecasting
Purpose: Develop a 24-month rolling forecast model for a healthcare company's customer journey, starting without historical data.

Core Business Flow:
- Primary customer journey: sign-up → appointment → prescription → delivery → refill → delivery
- Focus on prescription products only initially
- Virtual appointments only in initial model

Technical Requirements:
1. Python 3.11, Jupyter notebooks, Windows 11, TimesFM library
2. Daily forecasts rolling up to 24 months
3. Confidence intervals that widen over time
4. Configurable parameters for conversion rates between stages
5. Adjustable seasonality patterns (including but not limited to January spike)

Implementation Approach:
1. Base Parameters Module
   - Configurable conversion rates between stages
   - Stage-specific time delays
   - Seasonal patterns
   - Daily patterns (weekday/weekend effects)

2. Core Forecasting Components:
   - Base volume forecaster (daily new sign-ups)
   - Stage transition calculator
   - Confidence interval generator
   - Rolling retention calculator

3. Data Generation Flow Structure:
   - New Signups (with seasonality)
   - Appointment Scheduling (with delay + conversion rate)
   - Prescription Conversion (with conversion rate)
   - Initial Delivery (with delay + acceptance rate)
   - Refill Pattern (with retention decay)

Implementation Plan:
1. First iteration: Base flow with simple seasonality
2. Second iteration: Add confidence intervals
3. Third iteration: Add parameter adjustment capabilities
4. Fourth iteration: Refine seasonality and patterns

Future Considerations (not in initial implementation):
- Geographic distribution
- In-person appointments
- Non-prescription products
- Marketing campaign effects
- Referral program effects
- Capacity constraints
- Regulatory requirements
- Multiple customer journeys
- Provider availability
- Supply chain considerations
- Demographic factors
- Customer segmentation
- Customer experience feedback

Initial Assumptions:
- Linear customer retention fall-off
- Basic seasonal patterns
- Simple conversion rates between stages
- No capacity constraints
- No regulatory constraints

Success Criteria:
- Complete working code blocks
- Ability to generate 24-month forecasts
- Configurable parameters
- Reasonable confidence intervals
- Extensible structure for future enhancements