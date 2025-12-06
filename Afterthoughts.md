After propject completion, we discovered: Internal Eutrophication: How it works and what to do about it by AJP Smolders et all.  It provided some possible explanations for correlations seen in the PCA:

The addition of TEMP to our PCA analysis makes the relationship clearer.  Simply add 'TEMP' to var list in WQI_df, HPI_df, and the PCA, and add a block of code to produce NaNs where TEMP contains string in a few instances: 
for v in vars:
    bad = full_data[full_data[v].astype(str).str.contains("T/X", na=False)]
    if len(bad) > 0:
        print(v, bad[[v]])

full_data["TEMP"] = pd.to_numeric(full_data["TEMP"], errors="coerce")

## INSIGHTS paired with Internal eutrophication: How it works and what to do
about it - a review, A.j.p. smolders et all

In oxygenated systems, O is the primary electron acceptor (most thermodynamically favorable):
O2+4H+ + 4e- --> H2O
and will aid in the decay of organic matter:
C organic  + 2H2O --> CO2 + 4H+ + 4e-

In wetlands or eutrophic water, O limited.  -> nitrate is used as the terminal electron acceptor:
2NO3 + 12H+ + 10e- → N2 + 6H2O + NO3 + 9H+ + 8e- −→ NH+4 + 2H2O + OH-

The presence of sulphate reducing bacteria (SRB) and methanogenic bacteria (converting CO2 and acetate into methane) are essential for anaerobic decay.

Without the availability of nitrogen or in addition via other microbes, iron hydroxides and sulphate become involved at lower redox potentials.
FeOOH + 3H+ + e- -> Fe2+ + 2H2O
SO4 + 10H+ + 8e- -> H2S + 4H2O

Reduction of Fe and sulphate forms FeSx which can decrease P binding capacity.  FeS has fewer sorption sites (reactive spots on sediment where ions can attach - eating up anions like phosphate or bicarbonate) for P than iron hydroxides.  if phosphate is mobilized, it can further fuel aglal growth and eutrophication.     

This anoxic setup may be why we see a negative correlation with DO, sulfate, and Fe a positive correlation with N compounds and P in the water.  It's a system in oxygen depricated waters where subsequent redox pathways take precedence.

Alkalinity accelerates the process by helping break up the products of metabolism and allowing the microbes to keep going.   

Alkalinity increases biodegredation via microbes by allowing more phosphate uptake.  High sulphate reduction rates can drive more alkalinity and decreased Sulphate (see PC3). In the Winter, microbial reduction processes are greatly impaired by low temperatures, while the system is supplied with moderately buffered, sulphate rich groundwater, increasing SO4 concentrations and decreasing alkalinity. In most cases, Sulphate and alkalinity are negatively correlated.  Decay rate is a funciton of alkalinity instead of pH because bicarbonate neutralizes decay-inhibiting acids.

In the Winter, microbial reduction processes are greatly impaired by low temps, causing increased SO4 and decreased alkalinity.  This might be why we see positive sulphate correlations with negative temp correlations.  

Sulphate  concentrations have greatly increased because of erosion, agricultural leaching, and atmospheric sulphur (acid rain). 

If sulphate reduction continues, (creating FeS) toxic concentrations of free sulphide may accumulate in the sediment water and hurt rooted macrophytes through sulphide toxicity and iron deficiency.  Dissolved sulphide can further consume oxygen in the top sediment, causing even more anoxic conditions and killing off microbes that support balance in the ecosystem and breaking down of organic matter.  Benthivorous fish take the place of natural microbe decay, adding turbudity, erosion, and release of nutrients from soil.  We do not see a positive correlation with suspended solids under PC3, but this may be a function of polluted conditions in which even benthivorous fish have trouble due to the lack of oxygen and other factors.   

PC2 may correlate with a winter scenario in which a lot of sulfur is released due to colder temps.  Dissolved oxygen is high because of colder water and moderate photosynthesis, and microbe overdrive is curbed by the cooler temps.  There is further evidence of this in high salt contents from road runoff and high suspended solids due to lower water level.  Nitrate (positvely correlated PC2) is also a sulfate mobilizing agent.
