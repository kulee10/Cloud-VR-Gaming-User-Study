# Cloud-VR-Gaming-User-Study
This repo contains QoE user study data and model for cloud VR gaming
## Data
**uX_QoE.csv**: QoE data of each user. There are 33 sessions in a user study. Each session contains a specific scenario and its corresponding five QoE ratings, including *overall quality*, *visual quality*, *immersive level*, *cybersickness*, and *continue*. Noted that *100%*, *75%*, and *50%* in resolution represent *2880X1568*, *2112X1184*, and *1408X768*.

**user_info.csv**: GE and VE levels of all users. For GE levels, *1*, *2*, and *3* stand for *naive*, *intermediate*, and *advanced* gamers, respectively. As for VE levels, *0* means *no prior VR experience*.
## Model
**randomForest.sav**: The lightweight QoE model built from random forest regressor. 
    
    import pickle
    
    # load in the model
    model = pickle.load(open('./model/randomForest.sav', 'rb'))
    y = model.predict([bitrate, frame rate, width, height, delay, throughput, packet loss rate, VE level, GE level, SI, TI])
