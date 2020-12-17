# TP-3-BRAIN-TUMOR

•	Étape 1 : resize de l’image 

On resize l’image (240x240) on va alors printer les propriétés et resize de nouveau  (500x590)

•	Étape 2 :Thresholding

On convertit l’image à 3 canaux en image  grayscaleet 1 canal.   sur la grayImage avec Cv2.Treshold (src, treshold, maxValue , type(dst)) on applique une filtre seuil  binaire..  et enfin on inverse les valeurs du filtre cv2.THRESH_BINARY. 
On a ainsi converti l’image en niveaux de gris et l’image obtenue est utilisé pour le thresholding.

•	Étape 3 : transformation morphologique 

La nature de l’opération est déterminé par 2 entrées (kernel= src& element structurel), avec la fonction cv2.getStrucutingElement où l’on entre les dimensions du kernel (cv2.MORPH_RECT (10,5).
On utilise les opérateurs morphologiques d’érosion (cv2.erode(closed, None, iterations ) et de dilatation cv2.dilate(closed, None, iterations ). La dilatation suivi de l’érosion va permettre d’éliminer les points noir de la forme et combler les trous du font de la forme.Cv2.morphologyEx (im, cv2.MORPH_CLOSE, kernel) 

•	Étape 4 :  Canny Edge détection & contour

Sur l’image on va appliquer un autre filtre seuil binaire. Pour L’extraction de la forme de l’image on utilise la fonction cv2.bitwise. La fonction Auto _canny est définie pour calculer automatiquement les valeurs de seuil inférieure et supérieure cela va permettre d’appliquer le filtre Canny Edge detection. 
  Canny edge detection est fait sur l'image pour trouver le contour de la tumeur. (edged = cv2.Canny et
canny = auto_canny)
Le contour de la forme est  maintenant appliquer à l’image de base et le contour de la forme y est détecté. ( cv2.findContours et drawContours)

•	Étape 5 :calcul de l’aire

Via la fonction cv2.Area on peut calcer l’air de la forme qui le convertit en nombre de pixels constituant la forme.

Sources utilisées :
https://medium.com/@sanikamhadgut.nmims/brain-tumor-detection-and-classification-using-brain-mri-scans-368ed5533894
https://docs.opencv.org/3.4/d9/d8b/tutorial_py_contours_hierarchy.html
https://docs.opencv.org/master/d4/d73/tutorial_py_contours_begin.html
