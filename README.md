
## BI-REC: Guided Data Analysis for Conversational Business Intelligence

The technical report is added as a pdf file titled TechnicalReport.pdf.

Due to proprietary reasons, we cannot release the source code of BI-REC or the Health Insights dataset as both are held by the patent rights under the ownership of IBM.

We make the GoSales dataset used in the paper publicly available. Besides the appendix available in the paper, following is the information provided that helps in the reproducibility of our system BI-REC.

#### 1. /GoSales/Base-Ontology/

Under this folder, we have a file GOSALES_OLAP.owl which is the original ontology from the financial domain.

#### 2. /GoSales/syntheticVocabulary/

The additional synthetic measure groups and measures introduced into the ontology help us create a large-scale ontology that help a comprehensive evaluation of BI-REC. This folder contains the files corresponding to the synthetic ontology concepts (measure groups and measures) and the enhanced vocabulary.

#### 3. /GoSales/probabilityDistributions/

The files present here show how the sessions are distributed to the measure groups available in the ontology, as per various statistical distributions. The parameters for these distributions are in Table 1 in the paper. In order to reflect real human behavior and to preserve fairness by not giving our system a statistical advantage, we do not force all the measure groups to participate in the sessions.

#### 4. /GoSales/ST-Sessions/

- *ST-Exp*: Sessions following an exponential distribution are under this folder.
- *ST-Gamma*: Sessions following a gamma distribution.
- *ST-Normal*: Sessions following a normal distribution.
- *ST-Uniform*: Sessions following a uniform distribution.
	- *session_graph_noMeasGrp* - This prefix in a sessions file indicates the ontology expansion level "{BI}" described in the paper, that does not capture ontology neighborhood.
	- *session_graph_inclMeasGrp* - indicates the ontology expansion level "{BI, MG, EM}" that captures ontology neighborhood until expanded measures.
	- *session_graph_inclDimGrp* - indicates the ontology expansion level "{BI, MG, EM, DG}" that captures ontology neighborhood until dimension groups.
	- *session_graph_inclExpDim* - indicates the ontology expansion level "{BI, MG, EM, DG, ED}" that captures ontology neighborhood until expanded dimensions.
	
#### 5. /GoSales/BT-Sessions/

- *BT-Sessions-For-ST-Exp*: Sessions following various distributions for BI operation transitions between consecutive user queries or BI patterns are in this folder. The original workload used as the base workload is ST-Exp.
- *BT-Sessions-For-ST-Gamma*: BI transition variations for the default ST-Gamma workload.
- *BT-Sessions-For-ST-Normal*: BI transition variations for the default ST-Normal workload.
- *BT-Sessions-For-ST-Uniform*: BI transition variations for the default ST-Uniform workload.
	- *session_graph_inclMeasGrp_aug_MGSynth_A_BITrans_B_GoSales.csv* - This indicates that the ST-workload uses probability distribution *A* for sessions per measure group and the probability distribution *B* is used to determine the BI operator transition probabilities.

