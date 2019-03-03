# intro-data-capstone-biodiversity
import codecademylib
import pandas as pd
from matplotlib import pyplot as plt

# Loading the Data
species = pd.read_csv('species_info.csv')

print species.head()

species_count = species.scientific_name.nunique()
print species_count 

species_type = species.category.unique()

conservation_statuses = species.conservation_status.unique()
print conservation_statuses

species.fillna('No Intervention', inplace = True)

conservation_counts_fixed = species.groupby('conservation_status').scientific_name.nunique().reset_index()

print conservation_counts_fixed

import codecademylib
import pandas as pd
from matplotlib import pyplot as plt

# Loading the Data
species = pd.read_csv('species_info.csv')

print species.head()

species_count = species.scientific_name.nunique()
print species_count 

species_type = species.category.unique()

conservation_statuses = species.conservation_status.unique()
print conservation_statuses

species.fillna('No Intervention', inplace = True)

conservation_counts_fixed = species.groupby('conservation_status').scientific_name.nunique().reset_index()

print conservation_counts_fixed

import codecademylib
import pandas as pd
from matplotlib import pyplot as plt

# Loading the Data
species = pd.read_csv('species_info.csv')

print species.head()

species_count = species.scientific_name.nunique()
print species_count 

species_type = species.category.unique()

conservation_statuses = species.conservation_status.unique()
print conservation_statuses

species.fillna('No Intervention', inplace = True)

conservation_counts_fixed = species.groupby('conservation_status').scientific_name.nunique().reset_index()

print conservation_counts_fixed

import codecademylib
import pandas as pd
from matplotlib import pyplot as plt

# Loading the Data
species = pd.read_csv('species_info.csv')

print species.head()

species_count = species.scientific_name.nunique()
print species_count 

species_type = species.category.unique()

conservation_statuses = species.conservation_status.unique()
print conservation_statuses

species.fillna('No Intervention', inplace = True)

conservation_counts_fixed = species.groupby('conservation_status').scientific_name.nunique().reset_index()

print conservation_counts_fixed

import codecademylib
import pandas as pd
from matplotlib import pyplot as plt

species = pd.read_csv('species_info.csv')

species.fillna('No Intervention', inplace = True)

protection_counts = species.groupby('conservation_status')\
    .scientific_name.nunique().reset_index()\
    .sort_values(by='scientific_name')
print protection_counts

plt.figure(figsize = (10,4))
ax = plt.subplot()

bar_heights = protection_counts.scientific_name

plt.bar(range(len(protection_counts.conservation_status)), bar_heights)
ax.set_xticks(range(len(protection_counts.conservation_status)))
ax.set_xticklabels(protection_counts.conservation_status)
plt.ylabel('Number of Species')
plt.title('Conservation Status by Species')
plt.show()

import codecademylib
import pandas as pd
from matplotlib import pyplot as plt

species = pd.read_csv('species_info.csv')

species.fillna('No Intervention', inplace = True)

species['is_protected'] = species.conservation_status != 'No Intervention'

category_counts = species.groupby(['category', 'is_protected']).scientific_name.nunique().reset_index()

#print category_counts.head()

category_pivot = category_counts.pivot(columns='is_protected',
                      index='category',
                      values='scientific_name')\
                      .reset_index()
 

category_pivot.columns = ['category', 'not_protected', 'protected']

category_pivot['percent_protected'] = category_pivot.protected / (category_pivot.protected + category_pivot.not_protected)

print category_pivot

import codecademylib
import pandas as pd
from matplotlib import pyplot as plt

species = pd.read_csv('species_info.csv')

species.fillna('No Intervention', inplace = True)

species['is_protected'] = species.conservation_status != 'No Intervention'

category_counts = species.groupby(['category', 'is_protected']).scientific_name.nunique().reset_index()

#print category_counts.head()

category_pivot = category_counts.pivot(columns='is_protected',
                      index='category',
                      values='scientific_name')\
                      .reset_index()
 

category_pivot.columns = ['category', 'not_protected', 'protected']

category_pivot['percent_protected'] = category_pivot.protected / (category_pivot.protected + category_pivot.not_protected)

print category_pivot

import codecademylib
import pandas as pd
from matplotlib import pyplot as plt
from scipy.stats import chi2_contingency

contingency = [[30, 146],
              [75, 413]]

from scipy.stats import chi2_contingency

_, pval, _, _ = chi2_contingency(contingency)
print pval


contingency_reptile_mammal = [[30, 146],[5,73]]

_, pval_reptile_mammal, _, _ = chi2_contingency(contingency_reptile_mammal)
print pval_reptile_mammal

contingency_fish_mammal = [[30, 146],[11,115]]

_, pval_fish_mammal, _, _ = chi2_contingency(contingency_fish_mammal)
print pval_fish_mammal

contingency_nvplant_mammal = [[30, 146],[5,328]]

_, pval_nvplant_mammal, _, _ = chi2_contingency(contingency_nvplant_mammal)
print pval_nvplant_mammal

contingency_vplant_mammal = [[30, 146],[46,4216]]

_, pval_vplant_mammal, _, _ = chi2_contingency(contingency_vplant_mammal)
print pval_vplant_mammal

contingency_reptile_bird = [[5, 73],[75,413]]

_, pval_reptile_bird, _, _ = chi2_contingency(contingency_reptile_bird)
print pval_reptile_bird

contingency_amph_mammal = [[30, 146],[7,72]]

_, pval_amph_mammal, _, _ = chi2_contingency(contingency_amph_mammal)
print pval_amph_mammal

contingency_nv_v = [[5, 328],[46,4216]]

_, pval_nv_v, _, _ = chi2_contingency(contingency_nv_v)
print pval_nv_v

import codecademylib
import pandas as pd
from matplotlib import pyplot as plt
from scipy.stats import chi2_contingency

contingency = [[30, 146],
              [75, 413]]

from scipy.stats import chi2_contingency

_, pval, _, _ = chi2_contingency(contingency)
print pval


contingency_reptile_mammal = [[30, 146],[5,73]]

_, pval_reptile_mammal, _, _ = chi2_contingency(contingency_reptile_mammal)
print pval_reptile_mammal

contingency_fish_mammal = [[30, 146],[11,115]]

_, pval_fish_mammal, _, _ = chi2_contingency(contingency_fish_mammal)
print pval_fish_mammal

contingency_nvplant_mammal = [[30, 146],[5,328]]

_, pval_nvplant_mammal, _, _ = chi2_contingency(contingency_nvplant_mammal)
print pval_nvplant_mammal

contingency_vplant_mammal = [[30, 146],[46,4216]]

_, pval_vplant_mammal, _, _ = chi2_contingency(contingency_vplant_mammal)
print pval_vplant_mammal

contingency_reptile_bird = [[5, 73],[75,413]]

_, pval_reptile_bird, _, _ = chi2_contingency(contingency_reptile_bird)
print pval_reptile_bird

contingency_amph_mammal = [[30, 146],[7,72]]

_, pval_amph_mammal, _, _ = chi2_contingency(contingency_amph_mammal)
print pval_amph_mammal

contingency_nv_v = [[5, 328],[46,4216]]

_, pval_nv_v, _, _ = chi2_contingency(contingency_nv_v)
print pval_nv_v

import codecademylib
import pandas as pd
from matplotlib import pyplot as plt

species = pd.read_csv('species_info.csv')
species.fillna('No Intervention', inplace = True)
species['is_protected'] = species.conservation_status != 'No Intervention'

observations = pd.read_csv('observations.csv')
#print observations.head()

species['is_sheep'] = species.common_names.apply(lambda x: 'Sheep' in x)

species_is_sheep = species[species.is_sheep]
#print species_is_sheep

sheep_species = species[(species.is_sheep) & (species.category == 'Mammal')]

sheep_observations = observations.merge(sheep_species)

#print sheep_observations.head()

obs_by_park = sheep_observations.groupby('park_name').observations.sum().reset_index()

print obs_by_park

import codecademylib
import pandas as pd
from matplotlib import pyplot as plt

species = pd.read_csv('species_info.csv')
species.fillna('No Intervention', inplace = True)
species['is_protected'] = species.conservation_status != 'No Intervention'

observations = pd.read_csv('observations.csv')
#print observations.head()

species['is_sheep'] = species.common_names.apply(lambda x: 'Sheep' in x)

species_is_sheep = species[species.is_sheep]
#print species_is_sheep

sheep_species = species[(species.is_sheep) & (species.category == 'Mammal')]

sheep_observations = observations.merge(sheep_species)

#print sheep_observations.head()

obs_by_park = sheep_observations.groupby('park_name').observations.sum().reset_index()

print obs_by_park

import codecademylib
import pandas as pd
from matplotlib import pyplot as plt

species = pd.read_csv('species_info.csv')
species.fillna('No Intervention', inplace = True)
species['is_protected'] = species.conservation_status != 'No Intervention'

observations = pd.read_csv('observations.csv')
#print observations.head()

species['is_sheep'] = species.common_names.apply(lambda x: 'Sheep' in x)

species_is_sheep = species[species.is_sheep]
#print species_is_sheep

sheep_species = species[(species.is_sheep) & (species.category == 'Mammal')]

sheep_observations = observations.merge(sheep_species)

#print sheep_observations.head()

obs_by_park = sheep_observations.groupby('park_name').observations.sum().reset_index()

print obs_by_park

import codecademylib
import pandas as pd
from matplotlib import pyplot as plt

species = pd.read_csv('species_info.csv')
species['is_sheep'] = species.common_names.apply(lambda x: 'Sheep' in x)
sheep_species = species[(species.is_sheep) & (species.category == 'Mammal')]

observations = pd.read_csv('observations.csv')

sheep_observations = observations.merge(sheep_species)

obs_by_park = sheep_observations.groupby('park_name').observations.sum().reset_index()

plt.figure(figsize=(16, 4))
ax = plt.subplot()
bar_heights =obs_by_park.observations

plt.bar(range(len(obs_by_park.park_name)), bar_heights)

ax.set_xticks(range(len(obs_by_park.park_name)))
ax.set_xticklabels(obs_by_park.park_name)
plt.ylabel('Number of Observations')
plt.title('Observations of Sheep per Week')
plt.show()

baseline = 15

minimum_detectable_effect = 100*5./15
print minimum_detectable_effect
sample_size_per_variant = 870

yellowstone_weeks_observing = sample_size_per_variant/507.
print yellowstone_weeks_observing

bryce_weeks_observing = sample_size_per_variant/250
print bryce_weeks_observing

baseline = 15

minimum_detectable_effect = 100*5./15
print minimum_detectable_effect
sample_size_per_variant = 870

yellowstone_weeks_observing = sample_size_per_variant/507.
print yellowstone_weeks_observing

bryce_weeks_observing = sample_size_per_variant/250
print bryce_weeks_observing
