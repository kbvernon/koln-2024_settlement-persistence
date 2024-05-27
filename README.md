
# University of Cologne 2024 Settlement Persistence

<!-- badges: start -->
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
<!-- badges: end -->

Repository for my presentation at the [Advances in modelling past human ecosystems](https://ecosystem-modelling.uni-koeln.de/) workshop at the University of Cologne in Germany. Slides made using [quarto](https://quarto.org/) and R. 

__Slides:__ <https://kbvernon.github.io/koln-2024_settlement-persistence/>

You can press "F" to enter Full Screen mode and "S" to enter Speaker view. The hamburger button ☰ at the bottom left of the screen opens a menu that allows you to easily navigate the presentation.  

__Session:__ ""

__Title:__ "The network ecology of settlement persistence"

__Authors:__ K. Blake Vernon, Simon Brewer, Brian Codding, and Scott Ortman

__Abstract__  

**Research Question.** Why do some human settlements last longer than others?

**Aim.** The goal of this project is to evaluate the degree to which social and environmental factors contribute to the persistence of dispersed settlements within a small-scale agricultural system that evolved over several hundred years. 

**Inspiration.** Bird, Bocinsky, Reese, and Kohler (2024) Settlement persistence in the prehispanic central Mesa Verde Region: A dynamic analysis. [DOI: j.jasrep.2024.104515](https://doi.org/10.1016/j.jasrep.2024.104515)

**Motivation.** (1) This research integrates traditional survival analysis with the growing field of network ecology (Dale 2017, Fortin et al 2021) to evaluate the persistence of human settlements using properties of a graph, in this case node attributes (meaning, properties of the environment) and edge weights (or, social interactions). (2) Recent studies of persistence in ancient populations are concerned with the persistence of states (Scheffer et al 2023) and paradigmatic urban concentrations like towns and cities (Smith et al 2021, Lawrence et al 2023, Crawford et al 2023). This ignores settlement persistence at scales that preceded those larger concentrations and, importantly, lacked the highly centralized institutions that could impose meaningful constraints on individual behavior. (3) The large time scale of the analysis should offer insights into the role that climate change has played in shaping the relationship between socio-environmental dynamics and persistence. (4) By focusing on the persistence of small-scale agricultural settlements, this research will help shed light on the circumstances that eventually led to the evolution of cities (Smith and Lobo 2019, Ortman et al 2020). Finally, (5) because there is a time dimension to this, it may also help us to understand shifts from habitat exploration to habitat exploitation in settlement behavior (Bocinsky et al 2016).

**Data.** The study explores settlement persistence in three regions in the US Southwest: the central Mesa Verde region of southwest Colorado, the northern Rio Grande in New Mexico, and the Zuni or Cibola region on the border between Arizona and New Mexico. The time period of interest for this analysis is inclusive of the years from 1300 to 300 years BP (650 to 1650 CE), from the introduction of ceramics to the Spanish entrada. The study populations in these areas all practiced small-scale, subsistence maize farming, with mostly dispersed farmsteads early on that later aggregated into larger community centers (the timing of this varied by region). Representative data are provided by the Village Ecodynamics Project (Kohler et al 2012), the Southwest Social Networks Project (Mills et al 2013), and cyberSW (Mills et al 2020). The data include estimated start and end dates and room counts for each site.

**Methods.** (1) Social interaction is measured using weighted network centrality scores, where weights are based on travel times from every settlement to every settlement. Travel times are estimated by applying Dijkstra’s algorithm (Geisberger et al 2008) to a graph derived from an elevation model using Campbel’s hiking function (Campbell et al 2019). (2) Environmental data are provided by SKOPE (Bocinsky et al 2023), an open geospatial climate portal providing high resolution, gridded estimates of precipitation and temperature in the US Southwest over the last two millennia. These will serve as proxies for maize suitability in the project area. They are derived using a method established by Kyle Bocinsky known as paleoCAR, which models modern climate data as a function of the width of temporally aligned tree rings and then hindcasts climate estimates using older tree rings (Bocinsky et al 2014, 2016). (3) To model settlement longevity, the study will use a discrete time proportional hazards model (Suresh et al 2022). We prefer a discrete time model because it is frankly implausible to believe that we could get continuous measures of longevity given the amount of uncertainty around the true start and end dates for each settlement. The model is fit with Integrated Nested Laplace Approximation (INLA, Rue et al 2009, Gómez-Rubio 2020). In addition to being computationally efficient, INLA can also more readily incorporate a spatio-temporal covariance structure into the model. It is also easy to include hierarchical effects to account for differences in sampling and research methods in the three study regions and, at least potentially, any differences that are not captured by our primary measures of social interaction and environmental suitability.

**References**
Bocinsky, R. K., & Kohler, T. A. (2014). A 2,000-year reconstruction of the rain-fed maize agricultural niche in the US Southwest. Nature Communications, 5(1), 5618.
Bocinsky, R. K., Rush, J., Kintigh, K. W., & Kohler, T. A. (2016). Exploration and exploitation in the macrohistory of the pre-Hispanic Pueblo Southwest. Science Advances, 2(4), e1501532.
Bocinsky K., Gillreath-Brown A., Kintigh K., Kinzig A., Kohler T., Lee A., Ludäscher B., McPhillips T. (2023). Synthesizing Knowledge of Past Environments (SKOPE) Web Application (version v2023.10). DOI: 10.5281/zenodo.8415956 URL: https://app.openskope.org
Campbell, M. J., Dennison, P. E., & Thompson, M. P. (2022). Predicting the variability in pedestrian travel rates and times using crowdsourced GPS data. Computers, Environment and Urban Systems, 97, 101866.
Dale, M. R. (2017). Applying graph theory in ecological research. Cambridge University Press.
Fortin, M. J., Dale, M. R., and Brimacombe, C. (2021). Network ecology in dynamic landscapes. R. Soc. B. 288: 20201889. http://doi.org/10.1098/rspb.2020.1889
Geisberger, R., Sanders, P., Schultes, D., & Delling, D. (2008). Contraction hierarchies: Faster and simpler hierarchical routing in road networks. In Experimental Algorithms: 7th International Workshop, WEA 2008 Provincetown, MA, USA, May 30-June 1, 2008 Proceedings 7 (pp. 319-333). Springer Berlin Heidelberg.
Gómez-Rubio, V. (2020). Bayesian Inference with INLA. Chapman & Hall/CRC Press. Boca Raton, FL.
Kohler, T. A., Bocinsky, R. K., Cockburn, D., Crabtree, S. A., Varien, M. D., Kolm, K. E., ... & Kobti, Z. (2012). Modelling prehispanic Pueblo societies in their ecosystems. Ecological Modelling, 241, 30-41.
Mills, Barbara J., Jeffery J. Clark, Matthew A. Peeples, W. R. Haas, Jr., John M. Roberts, Jr., J. Brett Hill, Deborah L. Huntley, Lewis Borck, Ronald L. Breiger, Aaron Clauset, M. Steven Shackley (2013). The Transformation of Social Networks in the Late Pre-Hispanic U.S. Southwest. Proceedings of the National Academy of Sciences 110(15):5785-5790.
Suresh, K., Severn, C. & Ghosh, D. Survival prediction models: an introduction to discrete-time modeling. BMC Med Res Methodol 22, 207 (2022). https://doi.org/10.1186/s12874-022-01679-6
Mills, Barbara, Sudha Ram, Jeffery Clark, Scott Ortman, and Matthew Peeples. (2020). "cyberSW Version 1.0." Archaeology Southwest, Tucson.
Ortman, S. G., Lobo, J., & Smith, M. E. (2020). Cities: Complexity, theory and history. Plos one, 15(12), e0243621.
