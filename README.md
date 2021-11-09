# utilities

## Python code for formatting strings to datetimes using pandas
``` df['DataFrame Column'] = pd.to_datetime(df['DataFrame Column'], format=specify your format)
    formats: %Y - year, %m - month(1), %b - month(Ene), %d - day, %H - hour, %M - minutes, %S - seconds
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
