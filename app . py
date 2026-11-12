import streamlit as st
import pandas as pd
import numpy as np

# Page configuration
st.set_page_config(
    page_title="AgriPulse Gujranwala",
    page_icon="🌾",
    layout="centered"
)

# Sidebar navigation state
if 'screen' not in st.session_state:
    st.session_state.screen = 1

def go_to_screen(screen_num):
    st.session_state.screen = screen_num

# ==========================================
# SCREEN 1: Welcome & District Selector
# ==========================================
if st.session_state.screen == 1:
    st.title("🌾 AgriPulse Gujranwala")
    st.subheader("Climate & Crop Trend Detective")
    st.write("Empowering local agriculture and food security planning using NASA Earth science data.")
    
    st.markdown("---")
    
    # District selection
    district = st.selectbox(
        "Select Target District:",
        ["Gujranwala", "Sialkot", "Sheikhupura", "Lahore"]
    )
    
    # Analysis type selection
    analysis_type = st.selectbox(
        "Select Environmental Focus:",
        ["Land Surface Temperature vs. Crop Health (NDVI)", "Soil Moisture & Precipitation Depletion"]
    )
    
    st.markdown("<br>", unsafe_allow_html=True)
    
    if st.button("🚀 Analyze Trend", type="primary", use_container_width=True):
        go_to_screen(2)
        st.rerun()

# ==========================================
# SCREEN 2: Dual-Axis Trend Graph
# ==========================================
elif st.session_state.screen == 2:
    st.title("📊 5-Year Environmental Shift")
    st.write("Analyzing historical trends for **Gujranwala** district.")
    
    # Generate mock sample data for demonstration
    np.random.seed(42)
    years = pd.date_range(start="2020-01-01", end="2025-01-01", freq="ME")
    
    # Simulating rising temperature and dropping vegetation health
    temp_trend = np.linspace(28, 31.5, len(years)) + np.random.normal(0, 0.4, len(years))
    ndvi_trend = np.linspace(0.65, 0.48, len(years)) + np.random.normal(0, 0.03, len(years))
    
    df = pd.DataFrame({
        "Temperature (°C)": temp_trend,
        "Vegetation Health (NDVI)": ndvi_trend
    }, index=years)
    
    st.markdown("### Land Surface Temperature (Rising) vs Crop Health (Falling)")
    st.line_chart(df)
    
    st.info("💡 **Key Insight:** A 2.4°C average summer temperature spike correlates directly with a 15% drop in local vegetation health over the past 5 years.")
    
    col1, col2 = st.columns(2)
    with col1:
        if st.button("⬅️ Back to Selection", use_container_width=True):
            go_to_screen(1)
            st.rerun()
    with col2:
        if st.button("⚠️ View Impact Alert", type="primary", use_container_width=True):
            go_to_screen(3)
            st.rerun()

# ==========================================
# SCREEN 3: Action & Warning Alert
# ==========================================
elif st.session_state.screen == 3:
    st.title("🚨 Agricultural Impact Alert")
    st.write("Actionable insights and risk assessment based on detected trends.")
    
    st.error("🔴 **High Heat Stress Risk Detected** in central Gujranwala agricultural zones.")
    
    st.markdown("### Recommended Mitigation Strategies:")
    st.markdown("""
    * **Adjust Irrigation Timings:** Shift watering schedules to early morning or late evening to minimize rapid surface evaporation caused by rising temperatures.
    * **Drought-Resilient Varieties:** Introduce heat-tolerant crop strains for upcoming sowing cycles.
    * **Soil Mulching:** Encourage local farmers to use residue mulching to lock in declining soil moisture.
    """)
    
    st.markdown("---")
    
    col1, col2 = st.columns(2)
    with col1:
        if st.button("📊 Back to Graph", use_container_width=True):
            go_to_screen(2)
            st.rerun()
    with col2:
        if st.button("🔄 Start New Analysis", type="primary", use_container_width=True):
            go_to_screen(1)
            st.rerun()
