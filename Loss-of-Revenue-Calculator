import streamlit as st

# App Title
st.title("🎯 Student Ad ROI Calculator")

# Introduction
st.write(
    "Enter your ad campaign data below to calculate estimated conversions, revenue, "
    "and potential missed revenue due to inefficient targeting."
)

# User Inputs
ad_spend = st.number_input("Total Ad Spend ($)", min_value=0, value=50000, step=1000)
ctr = st.number_input("Click-Through Rate (CTR %)", min_value=0.0, value=1.2, step=0.1)
cvr = st.number_input("Conversion Rate (CVR %)", min_value=0.0, value=3.5, step=0.1)
cpa = st.number_input("Cost Per Acquisition (CPA $)", min_value=0.0, value=40.0, step=1.0)
revenue_per_conversion = st.number_input("Revenue Per Conversion ($)", min_value=0.0, value=200.0, step=10.0)

# Industry Benchmarks (for comparison)
benchmark_cvr = 5.0  # Midpoint of industry standard (4% - 6%)

# Calculations
estimated_clicks = ad_spend / (cpa / 100) if cpa > 0 else 0
estimated_conversions = estimated_clicks * (cvr / 100)
estimated_revenue = estimated_conversions * revenue_per_conversion
missed_revenue_opportunity = ((benchmark_cvr - cvr) / 100) * estimated_clicks * revenue_per_conversion if cvr < benchmark_cvr else 0

# Display Results
st.subheader("📊 Results")
st.metric("Estimated Clicks", f"{estimated_clicks:,.2f}")
st.metric("Estimated Conversions", f"{estimated_conversions:,.2f}")
st.metric("Estimated Revenue ($)", f"${estimated_revenue:,.2f}")
st.metric("Potential Missed Revenue ($)", f"${missed_revenue_opportunity:,.2f}")

# Conclusion & Next Steps
st.write(
    "**Want to optimize your student ad performance?** Consider refining your audience targeting, "
    "A/B testing creatives, and aligning campaigns with key student financial milestones."
)

st.write("🔹 **Benchmark Data:** Industry CVR: 4% - 6%, Average CPA: $25 - $50, ROAS Benchmark: 3:1.")

# Footer
st.markdown("---")
st.write("Powered by Sallie Mae Advertising Solutions")
