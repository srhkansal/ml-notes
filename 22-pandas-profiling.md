**automate data-visualization**
pip install pandas-profiling

from pandas_profiling import ProfileReport
profile = ProfileReport(df, title="Pandas Profiling Report", explorative=True)
profile.to_file("data_profile_report.html")
