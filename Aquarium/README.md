 # Transfer Learning with Frozen Layers

yolov5/train.py\
 # Freeze 
 freeze = []  # parameter names to freeze (full or partial) 
 for k, v in model.named_parameters(): 
     v.requires_grad = True  # train all layers 
     if any(x in k for x in freeze): 
         print('freezing %s' % k) 
         v.requires_grad = False 
\
freeze = ['model.%s.' % x for x in range(10)]  # parameter names to freeze (full or partial)
\
freeze = ['model.%s.' % x for x in range(24)]  # parameter names to freeze (full or partial)
\
!python train.py --img 416 --batch 16 --epochs 150 --data '../data.yaml' --cfg ./models/custom_yolov5s.yaml --weights yolov5s.pt --name yolov5s_results  --cache --hyp hyp.finetune.yaml 
\
