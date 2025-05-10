This project is an AI-powered detection tool for construction blueprints, specifically EV electrical plans. It identifies key electrical symbols like:
Trained weights are present in \YOLO_Finetune\runs\detect\train9\weights\best.pt
EV Chargers (`evse`)
Panelboards (`panel`)
GFI Receptacles (`gfi`)

I have used roboflow for augmenting and annotating the data and have trained the model using YOLOv8.
