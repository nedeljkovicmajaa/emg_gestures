- English

  - plan.txt - project work plan
  - link_DB2 - link to the database with the signals used in this work  
  - priprema 
             - vizualizacija_spektogram.py - code for signal visualization - spectrogram
             - CNN_model.py - code for the example CNN classifier and saving in the model  
             - evaluacija_modela.py - code for running the saved model and its evaluation
             - spectrogram.py - test code for spectrogram 
             - windowing.py - test code for windowing  
  - rad 
        - butterworth_filter.py - code for Butterworth filter implementation 
        - notch_filter.py - code for Notch filter implementation   
        - hampel_filter.py - code for Hampfel filter implementation  
        - spektrogram.py - code for Spectrogram visualization   
        - windowing.py - code for Windowing method  
        - CNN_window_non.py - code for CNN   
        - labele.py - code for forming the input matrix of the labels   
        - spajanje_fajlova.py - code for forming the input matrix of the datas for the CNN 
        - spectrogrami.py - merging spectograms of each chanal into one matrix  
        - spektrogram_podela.py - forming the single pictures
        - split_folders.py - code for separating the data into 3 sets - training, validation i test set  
  - Slike - accompanying material saved in the form of images

        Abstract
        
        Recognition of hand movements based on surface EMG signal processing (sEMG) has become a promising approach for upper limb neuroprosthesis control.
        The application of deep learning to sEMG data is a relatively new field of research aimed at finding adequate commercial prostheses that can enable movement
        control. The goal of this project is to recognize the position and movements of the hand based on sEMG signals (the classification of data into 17 classes -
        the number of movements and positions of the hand), using convolutional neural networks. It also investigates how the accuracy of classification is affected by
        different types of signal preprocessing. Signals from the NinaPro database were used and they are processed in different ways. This database is intended to study
        the relationship between surface electromyography, hand kinematics, and hand forces, with the ultimate goal of developing non-invasive, naturally controlled robotic
        hand prostheses. The signals used are quite narrow in scope and therefore very sensitive to rough processing, as most of them transmit hand movement information that
        is crucial for further classification. In addition to the noise that occurred due to the very nature of the movement of the hand and the movement of the signal
        collection apparatus, the occurrence of noise in the vicinity of 50Hz was also expected, because of some characteristics of the used electrodes. The preprocessing
        methods which are used are the Butterworth bandpass filter with bandwidth 30Hz-300Hz, bandstop Notch filter in the 50Hz frequency environment with Butterworth filter
        30Hz-300Hz, and Hampel filter. The processed signals, as well as the raw data, were visualized by the spectrogram method. The spectrogram transmits the signal
        strength using colors - the brighter the color, the higher the signal energy. By extracting the corresponding images from all 12 channels and merging them, one
        image was obtained. Each spectrogram corresponds to one repetition of one movement. The formed images represent the input of the neural network. The training was
        performed on all results and it was concluded that unfiltered signals give the best results of 86.9% validation accuracy. Signals pre-filtered with Butterworth
        filter, Notch filter, and Hampel filter give results of 82.8%, 69.4%, and 84.5% validation accuracy respectively. For each training session, confusion matrices were
        determined. From them, it can be noticed that the most commonly recognized movement is class 4, while the most commonly incorrectly determined movement is class 3.
        Classes 14, 16, and 17 are most often misinterpreted, while a very small number of classes are mistakenly recognized as class 10. Spectrum The assumption that the
        filtered signals will give the best results turned out to be wrong. This can also be attributed to the sensitivity of the signals themselves since the signal is mostly
        modified by a combination of bandstop and bandpass filters. This is confirmed by the fact that the result of Hampel signals, which is the least changed, is a few
        percent worse than the results of unfiltered signals.

-----------------------------------------------------------------------------------------------------

- Srpski

  - plan.txt - plan rada na projektu  
  - link_DB2 - link ka bazi sa signalima koje koristimo u radu  
  - priprema - Materijal pripremljen pre početka rada na projektu:  
             - vizualizacija_spektogram.py - kod za vizualizaciju signala spektrogramom  
             - CNN_model.py - kod za probni CNN klasifikator i  njegovo čuvanje u modelu   
             - evaluacija_modela.py - kod za pokretanje sačuvanog modela i njegova evaluacija  
             - spectrogram.py - probni kod za spectrogram  
             - windowing.py - probni kod za windowing  
  - rad - Zvaničan rad na projektu:  
        - butterworth_filter.py - kod za implementaciju butterworth filtera  
        - notch_filter.py - kod za implementaciju notch filtera  
        - hampel_filter.py - kod za implementaciju hampel filtera  
        - spektrogram.py - kod za vizualizaciju metodom spektrograma  
        - windowing.py - kod za windowing metodu  
        - CNN_window_non.py - kod za arhitekturu mreže  
        - labele.py - kod za formiranje ulazne matrice labela za mrežu  
        - spajanje_fajlova.py - kod za formiraje ulaznih matrica podataka za mrežu  
        - spectrogrami.py - spajanje spectrograma za svaki kanal posebno u jednu matricu  
        - spektrogram_podela.py - formiranje pojedinačnih slika  
        - split_folders.py - kod za podelu podataka u tri seta - trening, validaciju i set  
  - Slike - propratni materijal sačuvan u vidu slika  
  
        Apstrakt
        
        Cilj ovog rada je klasifikacija gestova šake obradom elektromiografskih signala i upotrebom konvolucionih neuronskih mreža. Korišćeni su signali iz NinaPro
        baze podataka koji su prvobitno procesirani na različite načine. Metode pretprocesiranja koje su se koristile bile su: Butterworth bandpass filtar sa propusnim
        opsegom od 30Hz do 300Hz, bandstop Notch filter u okolini frekvencije od 50Hz sa Butterworth filterom na frekvenciji od 30Hz do 300Hz i Hampel filter. Obrađeni, kao i
        sirovi podaci, vizualizovani su metodom spektrograma. Izdvajanjem odgovarajućih slika iz svih 12 kanala, i njihovim spajanjem, dobija se jedna slika. Svaki
        spektrogram odgovara jednom ponavljanju jednog pokreta. Formirane slike predstavljaju ulaz za odgovarauću neuronsku mrežu. Treniranje je izvršeno na svim
        podacima i zaključeno je da nefiltrirani signali daju najbolje rezultate od 87,6% test tačnosti. Signali prethodno filtrirani Butterworth filterom, Notch filterom i
        Hampel filterom daju redom rezultate od 82,8%, 69,4% i 84,5% validacione tačnosti. Za svako treniranje određene su matrice konfuzije sa kojih se može videti da je
        najčešće pogrešno prepoznat pokret je palac postavljen nasuprot malića (klasa 4), dok je najčešće pogrešno određen pokret ispruženi palac, kažiprst i srednji prst, dok
        su ostali savijeni (klasa 3). Najčešće tačno protumačene su klase 14 (istzanje ruke spolja), 16 (pomeranje šake ulevo) i 17 (istezanje pesnice), dok veoma mali broj
        klasa pogrešno prepoznat kao klasa 10 (okret raširene ruke udesno).
