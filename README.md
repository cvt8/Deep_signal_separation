# Deep_signal_separation

- Source tous le cours 8
- https://cloud.leviia.com/s/ZnIy.3xerJBY8PDKNrBL?path=%2FProjets%2FAudio%2Fsource_separation

Notre approche: Comparer seq2seq avec Unet et ConvTasnet.

## Séparation de sources 
L'objectif de ce projet est d'estimer conjointement la composante voix et la composante bruit d'un enregistrement audio.
Pour ce projet vous avez : 

Pour le train 
- Un dossier contenant des sous dossier numérotés (exemple 0001 ou 1256)
- Dans chaque sous dossier vous avez trois fichiers wav : mix_snr_XX.wav , voice.wav, noise.wav 
- voice.wav et noise.wav sont les vérités terrain à estimer, mix_snr_XX.wav est le mélange des deux sources avec un SNR de XX pour la composante voix (et de -XX pour la composante bruit) 

L'ensemble de test est constitué de la même façon. 

Vous pouvez au choix travailler 
- sur le spectrogramme par exemple en vous des approches par masquage présentés dans le cours  et en estimant les masques avec un réseau Seq2Seq de votre choix ou un UNet (cf A. Jansson et Al., SINGING VOICE SEPARATION WITH DEEP U-NET CONVOLUTIONAL NETWORK, ISMIR 2017 ) (https://openaccess.city.ac.uk/id/eprint/19289/1/7bb8d1600fba70dd79408775cd0c37a4ff62.pdf)
- avec la méthode Deep Clustering : J.R. Hershey et Al., Deep clustering: Discriminative embeddings for segmentation and separation, ICASSP 2016
- directement sur la forme d'onde  : 
   - cf D. Stoller  et Al., WAVE-U-NET: A MULTI-SCALE NEURAL NETWORK FOR END-TO-END AUDIO SOURCE SEPARATION, ISMIR 2018
   - les apporches TAS NEt : Y. Luo et Al., TaSNet: Time-Domain Audio Separation Network for Real-Time, Single-Channel Speech Separation, ICASSP 2018 ou Y. Luo et Al. (https://arxiv.org/pdf/1711.00541),  Conv-tasnet: surpassing ideal time–frequency magnitude masking for speech separation. IEEE/ACM Transactions on Audio, Speech, and Language Processing, 2019. (https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8707065)

Libre à vous de choisir la fonction de perte utilisée dans l’entraînement et adaptée au format des données que vous utiliserez en entrée du réseau de neurones. 
