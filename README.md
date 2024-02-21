\documentclass{article}
\usepackage[utf8]{inputenc}
\usepackage{gensymb}
\usepackage{graphicx} %package to manage images
\graphicspath{ {./images/} }
\usepackage{subfig}
\usepackage{float}
\usepackage[margin=1.0in]{geometry}


\title{Effects of Electromagnetic Radiation on Inactivating MS2 and SARS-Cov-Like Viruses}
\author{Skyler Granatir, Dr. Bo Marr, Dr. Bill Dower \\ Epirus Inc. \\ \texttt{skyler.granatir@epirusinc.com},\\ \texttt{bill@epirusinc.com}, \\ \texttt{marr.bo@gmail.com} }%
% \and  Madhavan Swaminathan, Yiliang Guo, \\Yifan Wang, Aaryan S. Shah \\ 3D Systems Packaging Research Center \\ Georgia Institute of Technology \\ \texttt{madhavan.swaminathan@ece.gatech.edu},\\ \texttt{yguo379@gatech.edu},\\ \texttt{yifanwang@gatech.edu},\\ \texttt{aaryan.s@gatech.edu} }}% 
%\date{October 2022}

\begin{document}

\maketitle

\section{Introduction}
\subsection{Abstract}
The COVID-19 pandemic presented a need for new technology to protect human life and Electromagnetic Pulse (EMP) technology has many applications in the sanitation, treatment and identification of different viruses including COVID-19. The effects of non-thermal EM radiation on Virus-Like Particles (VLPs) and MS2 bacteriophage, enveloped and non-enveloped viruses respectively, are studied and evaluated in this paper. We attempt to confirm a previous biophysical model that explains viral death under radiation, and we search for an economically feasible, quick, analytical way to measure a virus' EM susceptibility at different frequencies using a Coplanar Waveguide (CPW).   

\subsection{Motivation}
The experimental results shown in following sections lends possibilities of technological innovation. The penultimate section provides an outline of future technological innovation -- these are developments that can contribute to a society's ability to identify, sanitize, and treat viruses like SARS-CoV-2.  

\subsection{Previous Research and Modeling}
Previous research by Afaghi et. Al [4], posited that Cov-19 particles experience significant spike protein death at standard microwave radiation (2.45 GHz, ~15 kV/m).  It is important to note that this study observed 95\% spike protein denaturation, but did not report on the capsid survival or the subsequent infectiousness of the virus.  Due to geometric complexity of spike proteins, Epirus did not employ an in-depth physics and EM model to reduce the protein subsystem [5].

Yang et. Al [1] showed significant viral death on a larger scale, with the hypothesis that EM radiation can cause a rupturing of spherical influenza viruses.  By modeling a spherical virus as a sphere, and using Lamb's physics of an elastic sphere [3], the induced pressure on the viral shell was modeled as,

\begin{figure}[H]
    \centering
    \includegraphics[width=300]{images/stress_frequency}
\end{figure}

where $\omega$ is the experimental frequency and $\omega_0$ is the resonant frequency of the virus vibration.  By counting a plaque assay, this experiment was able to confirm the decrease in infectiousness of the virus due to viruses being destroyed by radiation [1].  While both these experiments showed viral degradation under EM radiation, the hypothesized method of inactivation are different.  For this reason, this paper also employs a round of testing that will help us better understand the mechanism of inactivation. 

\section{Experiment Setup}

\subsection{Hardware Setup}

The electronic system consists of a TEM Cell, function generator, signal generator, amplifier, and computer, as shown in Figure 1.  The waveform originates from a signal and function generator commanded by a computer.  The computer interfaces with the equipment to set parameters such as pulse width, input power, and frequency.  After the signal generator is triggered by the function generator, the signal is transmitted to a wideband amplifier (AR500M6G).  This electronic amp chain is shown in Figure 1.  The amplifier outputs a 180-250 W signal to the TEM Cell through N-type cables.  

\par Two TEM Cells are used for our experimentation, the Open OTEM 3000 and Tescom TC-5062C TEM Cells. The TEM Cells provide an enclosure that can provide predictable and powerful E-Fields (200 - 2000 V/m), at the point of petri dish, as shown to the right in Figure 1. The Open TEM required additional tent shielding to prevent radiation leakage.  The TC-5062C TEM Cell provides its own shielding, with up to 80 dB of attenuation.  In both setups, the leaked radiation at frequencies of interest is below 5 $mV/cm^2$, the FCC human safety threshold. 

It is worth noting that only the Tescom's electric field was able to be directly measured, at which we consistently saw ~10\% reduction in E-field compared to datasheet, likely caused by subtle impedance mismatching or EM interference around the probe cables.  We commonly used 180 W input power, which for Tescom corresponds to 413 V/m, and for OTEM 3000 corresponds to 2300 kV/m.  However, due to the fringent field effects of the OTEM 3000, this estimate is more likely to be ~1000-1800 V/m.

\par Immediately after each test, an infrared thermometer is used to measure the temperature of the viral buffer solution.  This is to ensure the solution stays below the critical temperature of SARS-Cov and VLPs ($149^o$ F).  If the MS2 or VLPs goes beyond its critical temperature, its inactivation may be due to the thermal interaction with the buffer, rather than electromagnetic excitation that this project attempts to investigate.  If temperatures rose beyond this temperature, the sample is discarded and the subsequent cool-down period between pulses is increased, giving the solution more time to cool down via convection.

\begin{figure}
    \centering
    \includegraphics[width=400]{nsf_test_setup}
    \caption{Nominal Test Setup}
    \label{fig:testSetup}
\end{figure}

\section{Coplanar Waveguide Investigation}
The COVID-19 pandemic spread worldwide within months and for the next pandemic identifying the frequency that destroys a specific virus is essential.  Through prior research (Liu et al., Yang et al.), Epirus furthered the development of a method to rapidly obtain the absorption spectrum of a virus enabling viral detection and EM sanitation.  By using a coplanar waveguide (CPW) in minutes we can identify which frequencies most effectively neutralize a virus.  
A CPW is a waveguide in which all conductors supporting wave propagation is placed on the same plane.  Active components can be placed along the microstrip as shown below. In previous literature (Liu et al., Yang et al.), the absorption spectrum of viral solutions is obtained by dripping 1 uL of viral solution uniformly along the microstrip [1].  Each end of the CPW is connected to a Vector Network Analyzer (VNA, CM M5065) which can emit and receive thousands of frequency points over a short interval.. 


\begin{figure}[H]%
    \centering
    \includegraphics[width=5cm]{images/cpw_drip.PNG}%
    \caption{Illustration of a VLP-Suspended Solvent on CPW}%
    \label{fig:example}%
\end{figure}


The absorption of any fluid along the microstrip line is modeled as, 

\[ 1 - |S_{21}|^2 - |S_{11}|^2 = A \]

Thus, a higher A implies a greater EM permittivity at a given frequency.  This permittivity can manifest in many energetic ways including rotation, stretching, lateral vibration, or heat generation within intramolecular bonds.  Results from the CPW are found in the section 4.3.

\section{Electromagnetic Pulses (EMP) destroys SARS-CoV-2 Virus Like Particles (SC2-VLPs}

\subsection{VLP Introduction}
VLP is a spherical, enveloped virus that is susceptible to the spheroidal vibration mode outlined by Lamb [3].  For samples treated $<$ 2 minutes, virus inactivation was not practically nor statistically observed. 
All data shown below corresponds to 8-10 minutes of radiation, at an input power of 180 W, corresponding to an E-field of 413 V/m in the Tescom TEM Cell, and ~1000-2000 V/m in the OTEM 3000. The theorized vibrational response of the virus is shown below.  

\begin{figure}[H]%
    \centering
    \subfloat[\centering Cov-19 Initial Condition]{{\includegraphics[width=5cm]{images/virus1.PNG} }}%
    \subfloat[\centering Intensified Stretching at t $>$ 0]{{\includegraphics[width=5cm]{images/virus2.PNG} }}%
    \caption{Spheroidal Vibration induced by Radiation.  The sphere experiences an intensifying stretch-compress cycle.}%
    \label{fig:example}%
\end{figure}

Elastic spheres carry an inherent L1, radial vibrational mode which is responsible for stretch-compress behavior on a small scale. Conceptually, this is similar to a 'breathing' vibration of the sphere.  In the hypothesis of Yang et al. [1], EM radiation couples with the intrinsic vibrational frequency of the virus and the sphere vibrates out of control and ruptures the wall of the virus.  

The other possible mechanism of viral degradation, introduced by Afaghi et. Al [4] is intramolecular heating in the spike proteins, which causes conformation or denaturation of the spike protein.  This would inhibit the virus' ability to bind to host cells. 

\subsection{SC2-VLP Materials and Methods}


\begin{figure}[H]%
    \centering
    {{\includegraphics[width=13cm]{images/experimental_Setup.PNG} }}%
    \caption{Experimental schematic for VLP setup.}%
    \label{fig:example}%
\end{figure}


Cell Lines and Plasmids: HEK293T (ATCC; CRL-3216) were maintained in complete DMEM (Thermo Fisher Scientific) media: 10\% Fetal Bovine Serum (FBS;Corning) and 1\% Penicillin/Streptomycin (Thermo Fisher Scientific). HEK293 cells expressing human ACE2 and TMPRSS2 (Invivogen ; hkb-hace2tpsa) were propagated in complete DMEM media supplemented with puromycin (0.5mg/ml), hygromycin B (200 mg/ml) and zeocin (100 mg/ml). 

Generation of SARS-CoV-2 Virus Like Particles (SC2-VLPs): 293T cells (3.5 x 106 in 10 mls total volume) were seeded in 10cm dishes 24 hours prior to transfection. The next day, 293T cells were transfected with a total of 20$\mu$ g plasmid according to the following molar ratios: 1 CoV2-N-WT-Hu1 (Addgene; 177937), 0.5 CoV-2-M-IRES-E (Addgene; 177938), 0.5 Luc-PS9 (Addgene; 177942) or Luc-noPS (Addgene; 177940) and 0.0125 CoV2Spike-EF1a-D614G-N501Y (Addgene; 177939). Plasmids were diluted in water to a final volume of 400 $\mu$L, along with 100$\mu$ L 2.5M calcium chloride (CaCl2) and 500$\mu$L 2X Hepes Buffered Saline (HBS; pH 7.05). This transfection mixture was vortexed, incubated for 1 minute at room temperature and added dropwise over the entire culture dish. To increase transfection efficiency, 10$\mu$ L of chloroquine (100mM) was added prior to returning cells to the incubator (37\degree C; 5\% CO2). Media was changed 16-18 hours post transfection. Forty-eight hours post transfection, supernatant (VLPs) was collected, clarified by centrifugation, filtered (0.45$\mu$ M PES), and stored at -80C. 

SC2-VLP infection and luciferase readout: In a clear, sterile, 96-well round-bottom plate, 30,000 293T-ACE2-TMPRSS2 cells were either left untreated or mixed with 50$\mu$L SC2-VLPs in triplicate. SC2-VLPs consisted of either negative controls (Luc-noPS), positive controls (Luc-PS9) or samples treated with various electromagnetic frequencies (EMPs). The cells and VLPs were incubated (37\degree C; 5\% CO2) overnight. The next day, supernatant was removed, cells rinsed with 100$\mu$L 1X PBS (ThermoFisher) and lysed with 20$\mu$L passive lysis buffer (Promega) for 15 minutes at room temperature with gentle rocking. The cells were then transferred to an opaque white 96 well plate, mixed with 50$\mu$L reconstituted luciferase assay buffer (Promega), and infectivity immediately measured on a luminometer (Biotek Synergy H1). The data was expressed as Relative Light Units (RLU).


\subsection{Coplanar Waveguide Measurements}
To explore the permittivity of the virus at a range of frequencies, we employ a coplanar waveguide (CPW) in combination with a Vector Network Analyzer (VNA) detailed in Section 3.  We drip Promega buffer solution along the microstrip and obtain an absorption spectra.  We then re-test with the conjoined buffer and VLP mix and subtract the contributions of the Promega buffer to obtain the absorption spectra of the VLP virus alone. This experiment was done on a Epirus fabricated CPW show in figure 2(a) The results of this experiment are shown in Figure 2(b).  As shown, a local peak occurs around 3.1 GHz and 6 GHz.  It should be noted that even without buffer on the CPW, we had previously observed resonance around 5-6 GHz, likely due to half-wavelength resonance, i.e. half-wavelength would geometrically fit across the CPW around these frequencies and bounce back-and-forth.  Nonetheless, when attempting to remove those contributions, we still witness significant absorption by the viruses at the higher frequencies.

\begin{figure}[H]%
    \centering
    \subfloat[\centering Epirus CPW Circuit]{{\includegraphics[width=5cm]{cpw_argos.png} }}%
    \qquad
    \subfloat[\centering VLP Absorption Spectra]{{\includegraphics[width=5cm]{images/cpw_vlp_results.png} }}%
    \caption{VLP Absorption by Frequency. $\Delta A $ reflects the amount of radiation absorbed by the VLPs.}%
    \label{fig:example}%
\end{figure}

\subsection{VLP Results}

The VLPs were found to be susceptible to EM radiation, with inactivation at multiple frequencies.  Figure 4 shows the average inactivation that occurred with radiation.  The dotted red lines show the  boundaries of the 2$\sigma$ 95\% confidence interval; thus any results that lie outside of this region have potential to be statistically significant results.  The survival of the viruses was directly measured, using an illumination method explained in 4.2, where the Relative Light Unit (RLU) indicates the illumination and thus population of survived viruses.

\begin{figure}[H]
    \centering
    \hspace*{-1cm}
    \includegraphics[width=400]{images/vlp_inactivation_new.png}
    \caption{Average Inactivation per frequency range.  Inactivation measured by 1 - $\mu_{treated} / \mu_{control}$, where $\mu_{control}$ is the average survival rate of controls.  Thus if the survival rate of the treated group is 40\%, and the survival rate of control group is 60\%, the relative inactivation is 1 - $40/60$, 33\%.  The virus had 33\% beyond baseline inactivation.}
    \label{fig:testSetup}
\end{figure}

\begin{figure}[H]
    \centering
    \hspace*{-1cm}
    \includegraphics[width=400]{images/nsf_frequency_barChart.png}
    \caption{Survival (measured by Relative Light Unit (RLU)) of different frequency ranges, plotted against controls.  These are the frequency ranges that hold statistical significance, with p-value plotted within bars. }
    \label{fig:testSetup}
\end{figure}

The most effective frequency studied was ~ 3.0 GHz.  There were 60 total vials analyzed, and we analyzed and averaged in groups of three, making 20 total triplicate samples.  When comparing the 3 GHz samples to the control group, we utilize a Wilcoxon Rank Sums Test [7], and receive a statistically significant p-value of 3.84e-5.  %By triplicate, we plot the 3 GHz averages and compare to the control group below. 

% \begin{figure}[H]
%     \centering
%     \hspace*{-1cm}
%     \includegraphics[width=400]{images/histogram_3ghz_vs_controls.png}
%     \caption{Plotting 3 GHz results next to control distribution.  RLU (x-axis) refers to the amount of illumination of the virus and linearly corresponds to the Survival of the virus.  Higher RLU implies a higher virus survival.  Wilcoxon Rank Sums Test yields p-value = 3.84e-5. }
%     \label{fig:testSetup}
% \end{figure}

There was no statistical significance in performance between the two TEM Cells, despite the OTEM predicted to deliver 2-3 kV/m, as opposed to 500 V/m of the Tescom.  For this reason, OTEM is likely underperforming to its predictions and needs more thorough testing to reveal its true E-field characteristics.  
    When comparing the experimental results to the predictions given by the Coplanar Waveguide, we can visualize an agreement
    in the figure below, where the average effect of radiation (given by 1/RLU) is plotted and overlayed with the results from Coplanar Waveguide (absorption of the VLPs at different frequencies).  Thus at frequencies that CPW predicted to interact heavily with VLPs, we observed the greatest inactivation.  With just a few pieces of equipment and a handful of minutes, it is possible to predict frequency-dependent susceptibility to radiation.
    
\begin{figure}[H]
    \centering
    \hspace*{-1.5cm}
    \includegraphics[width=8cm, scale=0.1]{images/cpw_vlp_results.png}
    \caption{Coplanar waveguide results, where a higher y-value, $\delta A$ corresponds to a larger permittivity and absorption of radiation into the virus.}
    \label{fig:testSetup}
\end{figure}
    
\begin{figure}[H]
    \centering
    \hspace*{-3cm}
    \includegraphics[width=500]{images/cpw_overlayed.png}
    \caption{The coplanar waveguide results (opaque curve) overlayed with the experimental effects of radiation (box plot).  Average effect of radiation is given by 1/RLU, where RLU is the illumination amount that describes the amount of survived viruses as explained in 4.4.}
    \label{fig:testSetup}
\end{figure}

\subsubsection{VLP Spike Protein Analysis}
To assess the mechanism of action by which EMP disrupts Covid infectivity, an experiment was chosen to assess any re-conformation of the Covid S-protein.  This would prove that the spike proteins are effected by EMP, and that the stretch-compress behavior outlined above was not the sole cause of decreased infectivity.  The hardware experimental procedure stayed the same, where we used the closed TESCOM-5602 to deliver 8 minutes of radiation around 300-500 V/m.  We used two previously successful frequencies at inactivating VLPs: 3.1 GHz and 5.9 GHz.  We also used a 1.9 GHz frequency as a negative-control.  The figure below illustrates our results.

\begin{figure}[H]%
    \centering
    \subfloat[\centering Results with 1:1 Dilution Ratio]{{\includegraphics[width=5cm]{images/day2_1_1.PNG} }}%
    \qquad
    \subfloat[\centering Results with 1:2 Dilution Ratio]{{\includegraphics[width=5cm]{images/day2_1_2.PNG} }}%
    \caption{Spike Protein concentration across previously shown effective frequencies (3.1, 5.9 GHz) and an ineffective frequency (1.9 GHz).}%
    \label{fig:example}%
\end{figure}

As shown in the figure, the spike binding was substantially reduced in the 3.1 GHz case.  This aligns with our previous findings where we saw decreased infectivity at this frequency.  However, the most surprising observation is that the 5.9 GHz trial, which also showed reduced infectivity, did not significantly affect the spike binding.  Further testing is required, but this potentially implies that the different frequencies may have different effects and mechanisms by which they decrease VLP's infectivity. 

\begin{figure}[H]
    \centering
    \includegraphics[width=380]{images/spike_destroy.PNG}
    \caption{A slight modification in structure inhibits the spike protein from cell entry [8]. }
    \label{fig:testSetup}
\end{figure}

As discussed, Afaghi et Al. [4] hypothesized that structural changes can be caused from localized heating, such as at salt bridges which can be irreversible.  Another hypothesis comes from Garcia et Al. [8] where it is possible that the permanent dipole in the protein side chain gets over stimulated and experiences irreversible structural change.  

\subsubsection{VLP Spike Protein Analysis Materials and Methods}

The SARS-CoV-2 Spike (S) protein performs two main functions: 1) attachment of the virus to the host cell receptor ACE2 and 2) viral entry into host cells via assisting in the viral fusion process. Spike contains two subunits: S1 and S2. S1 facilitates the attachment of the virus to ACE2 via its receptor binding domain (S1:RBD). Upon S1:RBD/ACE2 binding, the host protease TMPRSS2 cleaves Spike, exposing the S2 subunit to facilitate viral entry and fusion at the cell surface. An enzyme-linked immunosorbent assay (ELISA) can be used to quantitatively measure the amount of intact S1:RBD. In this assay, samples are placed into wells coated with an antibody specific for the SARS-CoV-2 S1:RBD. Critically, only conformationally intact S-protein will be able to bind the antibody. Once this occurs, a second antibody specific to SARS-CoV-2 S1:RBD is added which is conjugated to an enzyme. Addition of the enzyme’s substrate yields a detectable signal. We utilized an  S1:RBD ELISA to determine whether electromagnetic pulses (EMPs) could disrupt the conformation of Spike. S1:RBD binding decreased upon treatment with EMPs relative to non-treated samples, specifically at frequencies of 3.1 GHz. 

\section{EMP Effects on MS2 Bacteriaphage}

\subsection{Introduction}

MS2 is an icosahedral virus with a protein capsid.  These viruses have been well known to be robust in their heat and chemical resistance.  In the electromagnetic context, the icosahedral shape restricts the spheroidal vibration mode, outlined by Lamb [3], and thus the dipolar coupling mode outlined by Yang et. al [1].  Additionally, the Youngs Modulus of the protein capsid (~3 GPa) is much higher than the lipid bilayer in envelope viruses (20-200 MPa) [3] such as Cov-SARS,- VLPs, Influenzas, Ebola.  For this reason, MS2 is believed to remain structurally stable under MW radiation.  However, it is not clear how the binding proteins (maturation protein) behaves under radiation.  


\begin{figure}[H]
    \centering
    \includegraphics[width=150]{images/ms2_shape.jpg}
    \caption{The MS2 virus is an icosahedral shell with a stiff shell, making it a difficult virus to inoculate.}
    \label{fig:testSetup}
\end{figure}

\subsection{Specimen Culture and Setup}
Bacterial and viral stocks, reconstitution and growth/agar medium: Escherichia coli (E.Coli ; ATCC 15597) and Bacteriophage MS2 (ATCC 15597-B1) were grown in special medium recommended by ATCC (termed 271 broth). The media contained 10g tryptone, 1g yeast extract and 8g sodium chloride (NaCl) per liter of medium. Alternatively, to prepare soft agar, .45 g Agar (0.45\%) was also added.  After sterilization, the medium was cooled to ~50\degree C and supplemented with a filtered (0.22$\mu$M PES) solution containing glucose (0.1\%), CaCl2 (2 mM) and thiamine (10 $\mu$g/ml). Freeze-dried E. coli were reconstituted with 1 ml of 271 liquid broth. A few drops of the suspension were streaked on LB plates and incubated for 24 hours at 37C. Colonies were homogenized in 5 mls 271 liquid broth and grown at 37C until the bacteria reached early logarithmic phase ($OD_600$:0.2-0.4). One ml of this E. coli culture was added to reconstitute freeze-dried MS2. 

MS2 propagation and titer: Early log phase bacteria (5 mls) were infected with 100$\mu$L MS2 and incubated overnight (16-18 hours) at 37\degree C at 160RPM. The next day, the MS2 culture was centrifuged at 4000 x g for 10 minutes to separate host cell debris and bacteriophage. The supernatant was collected, filtrated (0.2$\mu$M PES filter), aliquoted, and stored at 4C. To titer MS2, 100$\mu$L of early log phase E. coli grown in 271 broth was combined with 4 mls soft agar (0.45\%) in a 14ml polypropylene tube. The mixture was lightly vortexed and aseptically added to a warm pre-made LB plate (1.5\% Agar). Serially diluted MS2 (10$\mu$L) was aseptically spotted into discrete sections of the plate and allowed to dry for 15 minutes prior to overnight incubation (16-18 hours) at 37\degree C. This yielded countable plaques on the 10-8 dilution and no visible plaques with our negative controls (bacteria or soft agar/buffer only). 

MS2 Plaque Assay: Prior to plating, MS2 (2 x 109 PFU/ml) was subjected to various electromagnetic frequencies (EMPs) or, as a positive control, UV irradiation (microwave) in triplicate. Early log phase E. coli (100$\mu$L) were then mixed with 10$\mu$L of treated or untreated MS2, lightly vortexed, and incubated for 10 minutes at room temperature. This bacteria/virus mixture was added to 4mls soft agar, lightly vortexed, and aseptically poured onto pre-warmed LB-agar plates. The plates were allowed to dry at room temperature prior to overnight incubation at 37\degree C. The next day, plaques were enumerated and the mean and standard deviation of each triplicate sample was calculated.  

\subsection{MS2 Results}
Over 10 distinct frequency points were tested in the range 800 MHz - 6 GHz.  Results are shown in Figure 2.  No specific frequency induced a mass extinction of the tested virus.  In fact, the only clear destruction occurred at 12 min of radiation in a standard 2.45 GHz microwave oven (p-value: 4.03E-5).  This viral death may have been due to heating, with temperatures reaching $>$ 150 $\degree$ F. We were unable to replicate this results with our own hardware, as 250 W input for 12 minutes would risk damaging the equipment.  

\begin{figure}[H]
    \centering
    \includegraphics[width=400]{images/MS2_Destruction.PNG}
    \caption{MS2 Survival Counts.  Grey region depicts the 90\% confidence interval of the Control group. }
    \label{fig:testSetup}
\end{figure}


\section{Possible Follow-On Development}

\subsection{In-Vivo & Selective Treatment}
Similar to last-resort treatment such as chemotherapy or radiation therapy, EMP can potentially be a treatment strategy that selectively targets in-vivo viruses without fatally affecting surrounding tissue. If a frequency exists such that a virus is ultimately susceptible, and surrounding human cells are unaffected, then EMP may be an effective, selective treatment that can target the virus, and only virus, within the human.  

\subsection{Industrial Coplanar Waveguide}
One of the most promising findings in this research was the ability to rapidly obtain the absorption spectrum of the virus by using a coplanar waveguide and VNA.  This gives us deeply insightful information about the permittivity and susceptibility of the virus to any given frequency. This can be done for more than viruses -- we can rapidly study the susceptibility of cell tissue, which allows us to predict the effects of radiation on cells such as human cell tissue. Diagnostics, therapeutics, research, and virus detection can all be simplified with this type of technology. 

\subsection{Covid Detector}
Similar to UV Spectroscopy, the coplanar waveguide technique can be used to detect Covid or any phage with a priori knowledge of the phage's absorption characteristics.  In a small portable system, a person can dip a swab, or breathe into a tube, and a VNA-like circuit can measure absorption at the most informative frequencies, from which a simple software model can use these measurements to classify whether the phage-of-interest exists in the sample. This can a diagnosis in a matter of seconds, compared to current rapid testing which takes 15 minutes.

\begin{figure}[H]
    \centering
    \includegraphics[width=350]{images/detector.PNG}
    \caption{Mock system diagram of a rapid assessment Covid detector based on RF response of the sample at certain characteristic frequencies emitted by the signal source. Sample can switch in and out between Ports P1 and P2.  }
    \label{fig:testSetup}
\end{figure}


\section{Conclusion}

In this research, we saw there were significant effects of EMP on the infectivity of VLP's, most notably at 3.1 GHz and 5.9 GHz. MS2, the hard, robust, icosahedral viruses was relatively unaffected.  The mechanism of action was also investigated on the VLPs by measuring the SARS-CoV-2 spike protein binding, witnessing reduced binding with incident 3.1 GHz radiation, and no significant change to binding with 5.9 GHz.  This may lend the hypothesis that the different frequencies had different effects on the virus, and thus the mechanism of inactivation may be different in the two cases.  

The recent COVID-19 pandemic has proved that modern methods are not sufficient to neutralize the virality of all infectious virus.  However there seems to be a breadth of possibility in the space of directed energy.  The power capability of GaN amplifiers are doubling every few years along with peripheral advancements that make EMP more enticing than ever before.  Thus the feasibility of technology outlined in Section 6 will be a convergence of ongoing rapid advancements in precision, power output, and cost of required hardware.  This project has uncovered future applications in therapeutics, sanitation, and diagnostics -- giving us crucial control over the virality of future viruses.  


\section{References}

1. Yang, SC., Lin, HC., Liu, TM. et al. Efficient Structure Resonance Energy Transfer from Microwaves to Confined Acoustic Vibrations in Viruses. Sci Rep 5, 18030 (2016). https://doi.org/10.1038/srep18030

2. Et-Thakafy O, Guyomarc'h F, Lopez C. Young modulus of supported lipid membranes containing milk sphingomyelin in the gel, fluid or liquid-ordered phase, determined using AFM force spectroscopy. Biochim Biophys Acta Biomembr. 2019 Sep 1;1861(9):1523-1532. doi: 10.1016/j.bbamem.2019.07.005. Epub 2019 Jul 8. PMID: 31295476.

3. Picas L, Rico F, Scheuring S. Direct measurement of the mechanical properties of lipid phases in supported bilayers. Biophys J. 2012 Jan 4;102(1):L01-3. doi: 10.1016/j.bpj.2011.11.4001. Epub 2012 Jan 3. PMID: 22225813; PMCID: PMC3250677.

4. Afaghi, P., Lapolla, M.A. & Ghandi, K. Denaturation of the SARS-CoV-2 spike protein under non-thermal microwave radiation. Sci Rep 11, 23373 (2021). https://doi.org/10.1038/s41598-021-02753-7

5. Brigandt, Ingo and Alan Love, "Reductionism in Biology", The Stanford Encyclopedia of Philosophy (Summer 2022 Edition), Edward N. Zalta (ed.), URL = <https://plato.stanford.edu/archives/sum2022/entries/ reduction-biology/>.

6. Abraham JP, Plourde BD, Cheng L. Using heat to kill SARS-CoV-2. Rev Med Virol. 2020 Sep;30(5):e2115. doi: 10.1002/rmv.2115. Epub 2020 Jul 2. PMID: 32614102; PMCID: PMC7361064.

7. Wild, Chris, University of Auckland. The Wilcoxon Rank-Sum Test (CH 10, 1997) https://www.stat. auckland.ac.nz/~wild/ChanceEnc/Ch10.wilcoxon.pdf

8. Arbeitman, C.R., Rojas, P., Ojeda-May, P. et al. The SARS-CoV-2 spike protein is vulnerable to moderate electric fields. Nat Commun 12, 5407 (2021). https://doi.org/10.1038/s41467-021-25478-7

\end{document}
