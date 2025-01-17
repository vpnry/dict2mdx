# Create venv first
```bash 
python3 -m venv .venv
source .venv/bin/activate
```

# install the modified version of pyglossary
https://drive.google.com/open?id=1bXm_PJUfZrcFX1zZAPC50DOsm4-gKlmJ

unzip, cd to it and run `python setup.py install` to install it to the venv
# install dependencies

- The most important dependencies:  
```bash 

pip install prompt_toolkit mdict-utils beautifulsoup4 python-lzo python-idzip

```

If there is an error for lzo, install this lib on your system: `sudo apt install liblzo2-dev`

- Other important dependencies:
```bash 

pip install lxml polib PyYAML beautifulsoup4 marisa-trie html5lib PyICU libzim

``` 

# generate
Remember to active the venv first `source .venv/bin/activate`
- Install the modified version of pyglossary, and dependencies.

- Copy Stardict dictionary data files to the directory where `dict2mdx.py` is located and run `python3 dict2mdx.py`
- Answer its questions:
  - Input `.ifo` output `.mtxt`.
  - Then convert to `.mtxt` then to `mdx`

For example:

```bash 
(.venv) ➜  v2.0.0 python3 dict2mdx.py
.script_history.txt not found. Ignoring on first run.
All dependings are ready!!

If your file is already .mtxt and/or sources folder and you want to convert directly to MDX and/or MDD press (y)!! OR press any other key if not! 
Your conversion will continue

> Input file: 2025_webster.ifo
> Output file: 2025_webster.mtxt
> Select action (ENTER to convert):
[INFO] Writing to OctopusMdictSource file '/home/p/pDEV/python-env/mdict-convert-pythonscript/v2.0.0/2025_webster.mtxt'
Converting: %99.8 |██████████████████████████████████████████████████████████████████████████████████████████████████▊|[00:01<00:00,  1.06s/it]
[INFO] Writing file '/home/p/pDEV/python-env/mdict-convert-pythonscript/v2.0.0/2025_webster.mtxt' done.
[INFO] Running time of convert: 1.2 seconds

If you want to repeat this conversion later, you can use this command:
pyglossary 2025_webster.ifo 2025_webster.mtxt --read-format=Stardict --write-format=OctopusMdictSource
> Press enter to exit, 'a' to convert again:


Convert .mtxt to MDX? (y) or press any other key to exit? y
Enter dict name again: 2025_webster.mtxt
Scan "2025_webster.mtxt": 98976

Pack to "2025_webster.mdx"
100%|████████████████████████████████████████████████████████████████████████████████████████████████| 98976/98976 [00:01<00:00, 89839.37rec/s]
                     --- Elapsed time: 2.019151 seconds ---                     
Scan "2025_webster.mtxt_res": 12

Pack to "2025_webster.mdd"
100%|████████████████████████████████████████████████████████████████████████████████████████████████████████| 12/12 [00:00<00:00, 123.02rec/s]
                     --- Elapsed time: 0.105965 seconds ---                     
Sources is also converted to MDD

All done!

```