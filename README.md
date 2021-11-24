# utilities

## Python code for formatting strings to datetimes using pandas
``` 
    formats: %Y - year, %m - month(1), %b - month(Ene), %d - day, %H - hour, %M - minutes, %S - seconds
    df['DataFrame Column'] = pd.to_datetime(df['DataFrame Column'], format=specify your format)
```

# Datetime formatting
``` 
    now = datetime.now()
    date_time = now.strftime("%m/%d/%Y, %H:%M:%S")
```

## Python codes for configuring virtual enviroments in jupyter lab
``` pip install jupyter lab
    python -m venv venv
    pip install ipykernel
    pip install -r requirements.txt
    python -m ipykernel install --user --name=venv
    jupyter kernelspec list
    jupyter kernelspec uninstall venv
```
## Time series checking for spurious correlation by checking percent changes instead of levels
``` 
    #correlation of level
    corr_levels = df1[feature1].corr(df1[feature2])
    ret = df1.pct_changes()
    corr_ret = ret[feature1].corr(ret[feature2])
    print(f'correlation of levels: {corr_levels}')
    print(f'correlation of changes: {corr_ret}')
```
