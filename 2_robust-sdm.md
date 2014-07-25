1. Robust and Dynamic Distribution Models
=========================================

Species distribution modeling literature and available techniques are
vast (Elith and Leathwick 2009). Predictive (vs explanatory) techniques
are broadly divisible as regression, such as generalized linear model
(GLM) or generalized additive model (GAM), or as machine learning, such
as multiple adaptive regression splines (MARS), boosted regression trees
(BRT), or maximum entropy (Maxent). MARS can uniquely produce a
multi-species response allowing for pooling of data, especially helpful
for rare species (Leathwick et al. 2006; Nally et al. 2008; Heinänen and
von Numers 2009). Multiple models can be combined as an ensemble (Araujo
and New 2007). Output can predict likelihood of presence (i.e. habitat)
or density (i.e. abundance per unit area). Some habitat modeling
techniques (e.g. Maxent) require only presence data, whereas others
require absence or pseudo-absence records. Density models require more
information on group sizes and parameters for detectability. Density
predictions enable the calculation of potential take, often required for
environmental impact assessment. Habitat requires less data and may be
more appropriate for determining go/no-go areas. Habitat has been
correlated to density for cetaceans in Scotland waters, but
inconsistently (Hall et al. 2010). Issues such as autocorrelation
(Dormann et al. 2007) and sampling bias (Phillips et al. 2009) need to
be addressed with each set of data.

Taking advantage of recently completed cetacean habitat models for US
Atlantic waters (Best et al. In Revision), I will compare performance of
modeling techniques ranging from presence-only to presence-absence to
density . These will include both correlative techniques (GLM, GAM) and
machine learning (random forest, BRT, Maxent). Does more information as
required by presence-absence and especially density add value? In order
to use both ship and plane datasets the cell values for fitting the GAMs
were offset residence time of survey effort per cell. No known methods
exist to simultaneously incorporate density surface models from
different platforms, so data will need to be subset for comparability.
Measures such as AUC will assess model performance. Megafauna often move
between several habitats depending on life stage while exhibiting
complex behaviors. They live in a dynamic world of shifting currents or
winds, temperature and prey. This compounds typical data limitations,
often resulting in species distributions having poor levels of variance
explained. Inclusion of dynamic variables could improve predictability.
The original models only included depth, distance to shore, distance to
continental shelf break, and sea-surface temperature (SST). The next
generation of models will include novel covariates from
satellite-derived features which tend to aggregate prey: improved
sea-surface temperature fronts, geostrophic eddies and the Lagrangian
technique finite-size Lyapunov exponent (Tew Kai et al. 2009). Mixed
layer depth (MLD) has proven to be a strong predictor for the habitat of
some cetaceans (Redfern et al. 2006), but has historically been limited
to in situ measurements by boat limiting its prediction across the
seascape. Now 4D oceanographic models such as the Hybrid Coordinate
Ocean Model (HyCOM) make MLD available over the entire oceanographically
modeled extent. Oceanographic models also do not suffer from cloud cover
and can resolve more finely in time and space, although error still
exists. Most importantly they can be used to forecast conditions.
California NOAA colleagues Elizabeth Becker and Karin Forney have been
extending their models (Becker et al. 2010) with the Regional
Oceanographic Modeling System (ROMS) to forecast in the Pacific. HYCOM
currently predicts out 5 days and ROMS up to 3 months. Most of these
data and tools relevant to US Atlantic are easily accessed within an
ArcGIS workflow through the Marine Geospatial Ecology Tools (Roberts et
al. 2010).

Adaptive management practices are emerging for responding to real-time
oceanographic features and endangered species observations. Hawaii-based
longline vessels in the Pacific are advised by a regularly update
satellite contour map from the TurtleWatch service to fish in waters
warmer than 65.5° C to avoid bycatch of loggerhead sea turtles (Howell
et al. 2008). A similar temperature contour was used for separation of
commercially fished tuna species in southwestern Australia (Hobday and
Hartmann 2006). All vessels larger than 65 ft around Boston Harbor must
travel 10 knots or less in critical habitat areas, and those heavier
than 300 gross tons must report entrance into key areas and respond in
real-time to current observations delivered through the right whale
sighting advisory system (Ward-Geiger et al. 2005). The notion of
pelagic reserves (Hyrenbach et al. 2000) is still young and has been
more recently suggested beyond countries' exclusive economic zones
(Ardron et al. 2008). The UN Convention on Biological Diversity is
reviewing criteria for Ecological and Biological Significant Areas for
applying these measures, organized in coordination with the Halpin lab
through the Global Ocean Biodiversity Initiative . In short a receptive
audience awaits for determining pelagic habitats with the latest
predictive tools relevant to policy in process (Dunn et al. 2010).
Dynamic management can include time-area closures, response to
environmental cues, and response to real-time observations. Whenever
considering these measures, the question to be asked is how much added
value does dynamic management provide in reducing risk versus cost for
additional management complexity? Scaling issues are pervasive in
ecology (Wiens 1989) and at least as relevant here. Grain of the
satellite imagery or oceanographic model is the limiting factor for
differentiating local behavior and response. For instance the
geostrophic currents is at about a 9km resolution. Many smaller-scale
oceanographic features exist relevant to species. From the minimal
resolution raster layers could be scaled to larger grain sizes to
evaluate the sensitivity and performance of the models at different
scales. This can similarly be done in time. A tradeoff generally exists
with finer temporal scales such as daily or weekly, suffering from more
missing data due to cloud cover. Larger scales, such as annual or
climatic, average out of existence significant ephemeral features like
SST fronts or geostrophic eddies.

Distribution of a species can lag in time and space from the
characterization of the environment, whether from remotely sensed data
or oceanographic models. The degree to which one is coupled to the other
may inform key ecological process, such as trophic linkages. For
instance, zooplanktivorous baleen whales, like the right whale feeding
on Calanus, are hypothesized to be respond more quickly and predictably
to the environment than pisciverous whales since more time is allowed
for drift. One study in South Africa boldly measured temperature,
chlorophyll, zooplankton, fish, bigger fish and birds, and found a
spatial mismatch in trophic linkages (Gremillet et al. 2008). Simple
testing of this drift in time between species and environment could
simply be accomplished by including lagged terms in the model and
allowing model selection to determine the best lag. Spatial lag would
test neighbors in space, hence testing 4 rook or 8 cardinal neighbors
per cell.

References
----------