# Healthcare Customer Churn Analysis

This project aims to analyze healthcare data to uncover insights regarding patient diagnoses, feedback, bed occupancy, and other important metrics. The analysis includes visualizations using PowerBI, Matplotlib, and Plotly.

## Table of Contents
- [Overview](#overview)
- [Datasets](#datasets)
- [Installation](#installation)
- [Usage](#usage)
- [Analysis and Visualizations](#analysis-and-visualizations)
- [PowerBI Dashboard](#powerbi-dashboard)
- [Matplotlib Visualizations](#matplotlib-visualizations)
- [Plotly Visualizations](#plotly-visualizations)
- [Contributing](#contributing)

## Overview

This project explores a healthcare dataset containing information about patient admissions, diagnoses, bed occupancy, tests conducted, and more. The goal is to derive meaningful insights through data analysis and visualizations.

## Datasets

Dataset : HealthCare-Dataset.csv

The dataset used in this project contains the following columns:
1. `Patient_ID`
2. `Admit_Date`
3. `Discharge_Date`
4. `Diagnosis`
5. `Bed_Occupancy`
6. `Test`
7. `Doctor`
8. `Followup_Date`
9. `Feedback`
10. `Billing_Amount`
11. `Health_Insurance_Amount`

## Installation

To run the analysis and visualizations, you'll need to have Python and the necessary libraries installed. Follow the steps below to set up the environment:

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/healthcare-data-analytics.git
    cd healthcare-data-analytics
    ```

2. Create and activate a virtual environment (optional but recommended):
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

### Required Libraries

Make sure the following libraries are installed:

- pandas
- numpy
- matplotlib
- plotly
- jupyter

You can install these libraries using the following command:
```bash
pip install pandas numpy matplotlib plotly jupyter
```

## Usage

1. **Running the Analysis**:
    - You can run the analysis scripts provided in the `Healthcare` folder. For example:
        ```bash
        python Healthcare/analysis.py
        ```

2. **Visualizations**:
    - To generate visualizations using Matplotlib and Plotly, run the respective scripts:
        ```bash
        python Healthcare/matplotlib_visualizations.py
        python Healthcare/plotly_visualizations.py
        ```

## Analysis and Visualizations
- Ensure all CSV files are in the same directory as main.py.
- Run the main script.

### PowerBI Dashboard

The PowerBI dashboard provides an interactive way to explore the healthcare data. It includes various charts and graphs to help users gain insights into patient diagnoses, feedback scores, bed occupancy, and more.

![PowerBI Dashboard Screenshot](https://github.com/pawanm07/HealthcareCustomerChurnAnalysis/blob/main/Dashboard%20img1.png)

### Matplotlib Visualizations

1. **Most Common Diagnoses**:
    ```python
    import matplotlib.pyplot as plt

    # Matplotlib bar chart
    plt.figure(figsize=(10, 6))
    diagnosis_counts.plot(kind='bar', color='skyblue')
    plt.title('Most Common Diagnoses')
    plt.xlabel('Diagnosis')
    plt.ylabel('Count')
    plt.xticks(rotation=45)
    plt.show()
    ```

2. **Feedback Scores Distribution**:
    ```python
    plt.figure(figsize=(10, 6))
    plt.hist(df['Feedback'], bins=10, color='lightgreen', edgecolor='black')
    plt.title('Distribution of Feedback Scores')
    plt.xlabel('Feedback Score')
    plt.ylabel('Count')
    plt.show()
    ```

3. **Bed Occupancy by Doctor**:
    ```python
    plt.figure(figsize=(10, 6))
    df.boxplot(column='Bed_Occupancy', by='Doctor')
    plt.title('Bed Occupancy by Doctor')
    plt.suptitle('')
    plt.xlabel('Doctor')
    plt.ylabel('Bed Occupancy')
    plt.show()
    ```

### Plotly Visualizations

1. **Most Common Diagnoses**:
    ```python
    import plotly.express as px

    # Plotly bar chart
    fig = px.bar(diagnosis_counts, x='Diagnosis', y='Count', title='Most Common Diagnoses')
    fig.update_layout(xaxis_title='Diagnosis', yaxis_title='Count')
    fig.show()
    ```

2. **Feedback Scores Distribution**:
    ```python
    fig2 = px.histogram(df, x='Feedback', title='Distribution of Feedback Scores',
                        nbins=10, opacity=0.75, color_discrete_sequence=['lightgreen'])
    fig2.update_layout(xaxis_title='Feedback Score', yaxis_title='Count')
    fig2.show()
    ```

3. **Bed Occupancy by Doctor**:
    ```python
    fig3 = px.box(df, x='Doctor', y='Bed_Occupancy', title='Bed Occupancy by Doctor')
    fig3.update_layout(xaxis_title='Doctor', yaxis_title='Bed Occupancy')
    fig3.show()
    ```

## Contributing
- Fork the repository.
- Create a new branch for your feature or improvement.
- Commit your changes and push to your fork.
- Create a pull request with a detailed description of your changes.
