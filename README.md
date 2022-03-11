# utilities

## PENDIENTE CUANDO HAGAS EL SORT_VALUES PORQUE SI LO HACES DIRECTO DEL INDEX SOLO MUEVE EL INDEX Y NO ARRASTRA LAS COLUMNAS CON EL (sortea todo el datafram by la columna que quieras)

## Python code for formatting strings to datetimes using pandas
``` 
    formats: %Y - year, %m - month(1), %b - month(Ene), %d - day, %H - hour, %M - minutes, %S - seconds
    df['DataFrame Column'] = pd.to_datetime(df['DataFrame Column'], format=specify your format)
```
## Datetime formatting
``` 
    now = datetime.now()
    date_time = now.strftime("%m/%d/%Y, %H:%M:%S")
```
## Python codes for configuring virtual enviroments in jupyter lab using pip
``` pip install jupyter lab
    python -m venv venv
    pip install ipykernel
    pip install -r requirements.txt
    python -m ipykernel install --user --name=venv
    jupyter kernelspec list
    jupyter kernelspec uninstall venv
```
## Python codes for configuring virtual enviroments in jupyter lab using conda
``` 
    # in anaconda prompt
    conda activate myvenv
    conda install -c anaconda ipykernel
    ipython kernel install --user --name=<any_name>
    conda deactivate
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
## Importing a custom module and avoiding errors by adding it to the path
```
    # importing custom util module from common directory
    sys.path.insert( 0, os.path.abspath("./common") )
    import util
```
## Finding distribution of data using Fitter
```
    conda install -c bioconda fitter
    conda install -c conda-forge easydev
    from fitter import Fitter, get_common_distributions, get_distributions
    f = Fitter(data, distributions = get_common_distributions())
    f.fit()
    f.summary()
```
## Downloading from google drive
```
    import gdown

    url = 'https://drive.google.com/uc?id=0B9P1L--7Wd2vNm9zMTJWOGxobkU'
    output = '20150428_collected_images.tgz'
    gdown.download(url, output, quiet=False)
    
    url = 'https://drive.google.com/drive/folders/1ivUsJd88C8rl4UpqpxIcdI5YLmRD0Mfj'
    gdown.download_folder(url, quiet=True, no_cookies=True)
```
## Installing a github repo in a conda enviroment
```
    conda install git
    conda intall pip
    # buscamos el repo y le quitamos la parte de http y agregamos .git al final
    https://github.com/Netflix/metaflow ---> //github.com/Netflix/metaflow.git
    #luego en el command colocamos
    pip install git+git://github.com/yourname/projectname.git
```
## Adding, Listing and removing anaconda kernels
```
    #Adding a kernel
    conda activate my_kernel
    ipython kernel install --name my-local --user
    
    #Listing kernels
    conda install -c anaconda jupyter
    jupyter kernelspec list
    
    #Removing a kernel
    jupyter kernelspec remove kernel-name
    
```
## SSAS connection using MSOLAP
``` 
    # Download ADOMD.net
    import pandas as pd
    from sys import path
    import clr
    
    # path al dll que descargaste "Microsoft.AnalysisServices.AdomdClient.dll"
    clr.AddReference(path)

    string = path
    path.append(string)

    from Microsoft.AnalysisServices.AdomdClient import AdomdConnection #, AdomdDataAdapter
    from System.Data import DataSet
    from pyadomd import Pyadomd

    conn_str = "Provider=MSOLAP;Data Source=<ip>;Initial Catalog=<nombre de la db>;Integrated                           Security=SSPI;Persist Security Info=false;DbpropMsmdFlattened2=true;User Id=<id>;Password=              <pass>;"
    
    query = "EVALUATE CONSOLIDADO"
    with Pyadomd(conn_str) as conn:
        with conn.cursor().execute(query) as cur:
            test = cur.fetchall()
    
```
