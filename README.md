# pfds
import pandas as pd

# Veri setini yükleme
url = "https://archive.ics.uci.edu/ml/machine-learning-databases/concrete/compressive/Concrete_Data.xls"
df = pd.read_excel(url)

# Sütun isimlerini basitleştirme (isteğe bağlı ama işlem kolaylığı sağlar)
df.columns = ['Cement', 'Blast_Furnace_Slag', 'Fly_Ash', 'Water', 'Superplasticizer', 
              'Coarse_Aggregate', 'Fine_Aggregate', 'Age', 'Concrete_compressive_strength']

# Korelasyon analizi
correlations = df.corr()['Concrete_compressive_strength'].sort_values(ascending=False)

# En yüksek korelasyona sahip 3 özellik:
# 1. Cement
# 2. Age
# 3. Superplasticizer
