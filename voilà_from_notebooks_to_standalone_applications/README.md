

https://blog.jupyter.org/and-voil%C3%A0-f6a2c08a4a93  
  
https://github.com/QuantStack/voila  
  


__Installation and first-time use__  
  
Voilà can be installed from pypi:  
  
pip install voila  
  
or conda-forge:  
  
conda install voila -c conda-forge  
  
Upon installation, several components are installed, one of which is the voila command-line utility.  
You can try it by typing voila notebook.ipynb. It results in the browser opening to a new tornado application   
showing markdown cells, rich outputs, and interactive widgets.  
  
__Richer layouts with Voilà templates__  
  
The main extension point to voilà is the custom template system. The HTML served to the end-user is produced  
from the notebook model by applying a Jinja template, which can be defined by the user.  
  
An example template for voilà is the voila-gridstack template, which can be installed from pypi with  
  
pip install voila-gridstack  
  
You can try it by typing voila notebook.ipynb --template=gridstack.  
