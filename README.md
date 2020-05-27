本存储库的构建于论文《基于生成对抗网络的零样本图像分类》
论文地址：https://bhxb.buaa.edu.cn/CN/abstract/abstract14960.shtml

相关说明如下：

1.代码运行环境
    numpy  1.17.2
    scipy     1.3.1
    torch     0.3.1
    
2.数据集下载：http://datasets.d2.mpi-inf.mpg.de/xian/xlsa17.zip

3.FD-fGAN-Attention模型为添加注意力的FD-fGAN

4.FD-fGAN运行样例：
# zsl_awa
CUDA_VISIBLE_DEVICES=2 python gan.py --manualSeed 9182 --cls_weight 0.01 --preprocessing --val_every 1 --lr 0.00001 --cuda --image_embedding res101 --class_embedding att --netG_name MLP_G --netD_name MLP_CRITIC --nepoch 70 --syn_num 300 --ngh 4096 --ndh 4096 --lambda1 10 --critic_iter 5 --dataset AWA1 --batch_size 64 --nz 85 --attSize 85 --resSize 2048 --outname awa 
# gzsl_awa
CUDA_VISIBLE_DEVICES=2 python gan.py --gzsl --manualSeed 9182 --cls_weight 0.01 --preprocessing --val_every 1 --lr 0.00001 --cuda --image_embedding res101 --class_embedding att --netG_name MLP_G --netD_name MLP_CRITIC --nepoch 70 --syn_num 1800 --ngh 4096 --ndh 4096 --lambda1 10 --critic_iter 5 --nclass_all 50 --dataset AWA1 --batch_size 64 --nz 85 --attSize 85 --resSize 2048 --outname awa 

# zsl_cub
CUDA_VISIBLE_DEVICES=3 python gan.py --manualSeed 3483 --val_every 1 --cls_weight 0.01 --preprocessing --cuda --image_embedding res101 --class_embedding att --netG_name MLP_G --netD_name MLP_CRITIC --nepoch 70 --ngh 4096 --ndh 4096 --lr 0.0001 --classifier_lr 0.001 --lambda1 10 --critic_iter 5 --dataset CUB --batch_size 64 --nz 312 --attSize 312 --resSize 2048 --syn_num 300 --outname cub
# gzsl_cub
CUDA_VISIBLE_DEVICES=2 python gan.py --gzsl --manualSeed 3483 --val_every 1 --cls_weight 0.01 --preprocessing --cuda --image_embedding res101 --class_embedding att --netG_name MLP_G --netD_name MLP_CRITIC --nepoch 70 --ngh 4096 --ndh 4096 --lr 0.0001 --classifier_lr 0.001 --lambda1 10 --critic_iter 5 --dataset CUB --nclass_all 200 --batch_size 64 --nz 312 --attSize 312 --resSize 2048 --syn_num 300 --outname cub

# zsl_sun
CUDA_VISIBLE_DEVICES=2 python gan.py --manualSeed 4115 --cls_weight 0.01 --val_every 1 --preprocessing --cuda --image_embedding res101 --class_embedding att --netG_name MLP_G --netD_name MLP_CRITIC --nepoch 70 --ngh 4096 --ndh 4096 --lambda1 10 --critic_iter 5 --dataset SUN --batch_size 64 --nz 102 --attSize 102 --resSize 2048 --lr 0.0002 --classifier_lr 0.0005 --syn_num 100 --outname sun 
# gzsl_sun
CUDA_VISIBLE_DEVICES=2 python gan.py --gzsl --manualSeed 4115 --cls_weight 0.01 --val_every 1 --preprocessing --cuda --image_embedding res101 --class_embedding att --netG_name MLP_G --netD_name MLP_CRITIC --nepoch 70 --ngh 4096 --ndh 4096 --lambda1 10 --critic_iter 5 --dataset SUN --batch_size 64 --nz 102 --attSize 102 --resSize 2048 --lr 0.0002 --syn_num 400 --classifier_lr 0.001 --nclass_all 717 --outname sun 


