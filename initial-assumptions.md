Business Model Questions:

1. Is there a typical customer journey? (e.g., sign-up → appointment → prescription → subscription)
   1. customer journey1: sign-up → appointment → prescription → delivery > refill  > delivery
   2. For now, we will focus on customer journey1, just to keep it simple, but we'll add other customer journeys future analysis, and if  it makes a sidficant difference in architecture build to support this.
2. Are these weight-loss products exclusively prescription-based, or is there a mix of Rx and non-Rx products?
   1. There are both prescription and non-prescription products, but for now we're only modelling the prescription products.
3. Do you have any known seasonality in the business? (Many weight-loss companies see January spikes)
   1. Yes, there is a known seasonality in the business, with spikes in January. Let's also seek out info later on other potential seasonality patterns.
4. What's the typical retention period for customers?
   1. We'll need to model this based on fall-off at each point in the customer journey. We'll solve this with a function, which initially we'll assume is linear, but we'll refine this as we get more data.
5. Are there any regulatory requirements that might affect the business? (e.g., prescription refills)
   1. Yes, there are regulatory requirements that affect the business. We'll not include these in the initial model, but we'll add if needed

Operational Questions:

1. Are appointments virtual or in-person or both?
   1. Appointments are virtual, but we'll add in-person appointments in the future.
2. Is there geographic distribution we need to consider?
    1. Yes, there is a geographic distribution we need to consider. We'll add this in the future. For now we'll assume it's a total customer base. Later we will add factors like geography, demographics, etc.
 3. What's the capacity constraint on appointments? (This could affect new customer acquisition)
    1. Unknown for now, but we'll add this in the future.
 4. Are prescriptions tied to specific regulatory requirements that might affect refill patterns?
    1. Unknown for now, but we'll add this in the future.

Marketing Questions:

1. Do you run regular marketing campaigns that might create spikes in sign-ups?
Is there a referral program that creates network effects?
    1. Yes, there are regular marketing campaigns that create spikes in sign-ups. We'll add this in the future.
    2. Yes, there is a referral program that creates network effects. We'll add this in the future.

Recommended Approach:
Given the multiple interconnected components, I suggest we:

1. Create a hierarchical forecasting structure:
   1. Top level: Total customer base
   2. Second level: Major funnel stages (Acquisition, Active Customers, Churned)
   3. Third level: Detailed metrics within each stage


2. Build related but separate models for:
   1. New customer acquisition pipeline (sign-ups → appointments → enrollments)
   2. Product demand (prescriptions, non-Rx orders, refills)
   3. Retention/churn predictions



So in conclusion, we'll start with a simple model that captures the main customer journey, and then we'll add complexity as we get more data and refine our assumptions.