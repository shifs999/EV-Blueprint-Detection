## EV-Blueprint-ElectricSymbol-Detection
---

This project is a basic electrical symbols detection tool for construction blueprints, specifically EV electrical plans. It identifies key electrical symbols like:

EV Chargers (`evse`)
Panelboards (`panel`)
GFI Receptacles (`gfi`)

I have used roboflow for augmenting and annotating the data and have trained the model using YOLOv8.
Trained weights can be found [here.](\YOLO_Finetune\runs\detect\train9\weights\best.pt)

---

 Input file type : PNG, JPG, or single-page PDF of blueprint as shown in an example input below: 
<img src = "YOLO_Finetune/content/E003.png">

 Output (JSON):

{
  "detections": [
    {
      "label": "evse",
      "confidence": 0.91,
      "bbox": [x, y, width, height]
    }
  ],
  "image_url": "/file=.../overlay.png"
}

The detections will be displayed in JSON format as above, with a confidence score telling how sure the model is about the prediction on respective label. For good measure, only those detections should be accounted as correct where confidence parameter is greater than `0.6`.

---
Upon testing on the blueprint image below: <img src = "YOLO_Finetune/content/E004.png">
The model classified 14 out of 19 `evse` symbols, 1 out of 1 `gfi` and `panel` symbols with a confidence interval of greater than `0.6`, thus predicting the symbols with an overall accuracy of approximately `77%`.
