# Natural Disasters Data Analysis Project (1974-2024)

A comprehensive data analysis project examining natural disasters over the past 50 years, providing insights into temporal trends, geographical patterns, and disaster impact assessments.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Data Structure](#data-structure)
- [Output Files](#output-files)
- [Analysis Components](#analysis-components)
- [Visualizations](#visualizations)
- [Dependencies](#dependencies)
- [Contributing](#contributing)
- [License](#license)

## 🌍 Overview

This project analyzes natural disasters from 1974 to 2024, examining patterns in:
- Disaster frequency and severity trends
- Geographical distribution and risk assessment
- Economic impact and human casualties
- Seasonal and temporal patterns
- Risk scoring for different countries and regions

The analysis uses synthetic data that mimics real-world disaster patterns and can be easily adapted to work with actual datasets from sources like EM-DAT, NOAA, or USGS.

## ✨ Features

### Core Analytics
- **Temporal Trend Analysis**: Track disaster frequency, deaths, and economic damage over time
- **Geographical Risk Assessment**: Identify high-risk countries and regions
- **Disaster Type Classification**: Analyze 8 different disaster categories
- **Severity Scoring**: Classify disasters from Minor to Catastrophic
- **Moving Average Calculations**: Smooth trend identification with 5-year moving averages

### Advanced Features
- **Risk Score Calculation**: Composite risk scoring for countries
- **Correlation Analysis**: Identify relationships between different impact metrics
- **Pattern Recognition**: Seasonal patterns and trend identification
- **Interactive Visualizations**: HTML-based interactive charts using Plotly

## 🚀 Installation

### Prerequisites
- Python 3.7+
- Required packages (see [Dependencies](#dependencies))

### Setup
1. Clone the repository:
```bash
git clone https://github.com/yourusername/natural-disasters-analysis.git
cd natural-disasters-analysis
```

2. Install required packages:
```bash
pip install pandas numpy matplotlib seaborn plotly requests
```

3. Run the analysis:
```bash
python disaster_analysis.py
```

## 📊 Usage

### Basic Usage
```python
from disaster_analysis import NaturalDisasterAnalysis

# Initialize analyzer
analyzer = NaturalDisasterAnalysis()

# Load sample data
analyzer.load_sample_data()

# Process data
analyzer.clean_and_process_data()

# Generate summary statistics
summary = analyzer.generate_summary_statistics()
print(summary)
```

### Advanced Usage
```python
# Generate risk scores
risk_scores = analyzer.calculate_risk_scores()

# Analyze temporal trends
yearly_trends = analyzer.analyze_temporal_trends()

# Create visualizations
temporal_fig = analyzer.plot_temporal_trends()
type_fig = analyzer.plot_disaster_type_analysis()

# Generate comprehensive report
report = analyzer.generate_report()
```

### Running the Complete Analysis
Simply execute the main script:
```bash
python disaster_analysis.py
```

## 📁 Data Structure

The analysis works with the following data structure:

| Column | Type | Description |
|--------|------|-------------|
| year | int | Year of disaster occurrence |
| disaster_type | str | Type of disaster (Earthquake, Flood, Storm, etc.) |
| country | str | Country where disaster occurred |
| continent | str | Continent classification |
| deaths | int | Number of deaths caused |
| affected_people | int | Number of people affected |
| economic_damage_usd | float | Economic damage in USD |
| magnitude_intensity | float | Disaster magnitude/intensity |
| date | datetime | Specific date of occurrence |
| decade | int | Decade classification |
| severity | str | Severity classification (Minor, Moderate, Major, Catastrophic) |

## 📈 Output Files

The analysis generates the following files:

### Visualizations
- `temporal_trends.png` - Time series analysis of disaster trends
- `geographic_heatmap.png` - Heatmap showing deaths by continent and disaster type
- `severity_distribution.png` - Distribution charts for disaster severity
- `disaster_type_analysis.html` - Interactive Plotly dashboard

### Data Files
- `processed_disaster_data.csv` - Cleaned and processed dataset
- `natural_disasters_report.txt` - Comprehensive text report

## 🔍 Analysis Components

### 1. Data Collection & Preparation
- **Sample Data Generation**: Creates realistic synthetic disaster data
- **Data Cleaning**: Handles missing values and data validation
- **Feature Engineering**: Adds calculated fields like decade and severity classification

### 2. Exploratory Data Analysis
- **Summary Statistics**: Key metrics and overview statistics
- **Temporal Analysis**: Trends over time with moving averages
- **Geographical Analysis**: Regional distribution and patterns
- **Disaster Type Analysis**: Comparative analysis across disaster types

### 3. Advanced Analytics
- **Risk Scoring**: Composite risk assessment for countries
- **Pattern Recognition**: Identification of trends and seasonal patterns
- **Correlation Analysis**: Relationships between different metrics

### 4. Reporting
- **Automated Report Generation**: Comprehensive text reports
- **Data Export**: Processed datasets for further analysis

## 📊 Visualizations

The project generates multiple types of visualizations:

### Static Plots (Matplotlib/Seaborn)
- **Temporal Trends**: Line plots showing disaster frequency, deaths, and economic damage over time
- **Geographic Heatmap**: Heat map visualization of disaster impacts by region
- **Severity Distribution**: Pie charts and stacked bar charts showing severity patterns

### Interactive Visualizations (Plotly)
- **Disaster Type Dashboard**: Interactive bar charts comparing different disaster types
- **HTML Export**: Shareable interactive visualizations

## 📦 Dependencies

```python
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
plotly>=5.0.0
requests>=2.25.0
```

Install all dependencies:
```bash
pip install -r requirements.txt
```

## 🛠️ Customization

### Using Real Data
To use real disaster data instead of synthetic data:

1. Replace the `load_sample_data()` method with your data loading logic
2. Ensure your data matches the expected column structure
3. Update any data-specific parameters in the analysis methods

### Adding New Disaster Types
```python
disaster_categories = ['Earthquake', 'Flood', 'Storm', 'Drought', 
                      'Wildfire', 'Volcanic', 'Landslide', 'Extreme Temperature',
                      'Your_New_Type']  # Add new types here
```

### Modifying Risk Scoring
Update the `calculate_risk_scores()` method to include additional factors:
```python
def calculate_risk_scores(self):
    # Add your custom risk factors here
    country_risk = self.processed_data.groupby('country').agg({
        'disaster_type': 'count',
        'deaths': 'mean',
        'your_custom_metric': 'mean'  # Add custom metrics
    })
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Data structure inspired by EM-DAT (Emergency Events Database)
- Visualization techniques adapted from best practices in disaster risk analysis
- Statistical methods based on established disaster assessment frameworks
