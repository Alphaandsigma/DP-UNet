# DP-UNet
DP-UNet
# #PFP block
# from tensorflow.keras import layers, Model
# def pyramid_feature_maps(inp,IMG_SIZE,feature_width, blockname):
#     x1 =MaxPooling2D(pool_size=(2,2),padding='same',name=blockname+'x1_pool')(inp)
#     print('x1pooling.shape{}'.format(x1.shape))
#     x1_upsampled =UpSampling2D(size=2, interpolation='bilinear', name=blockname+'x1_upsampling')(x1)
#     print('x1upsampling.shape{}'.format(x1_upsampled.shape))
#     concate_one=concatenate([inp,x1_upsampled])
#     print('x1concatenate.shape{}'.format(concate_one.shape))
#     # print('concate_one.shape{}'.format(concate_one))

#     # x2 = MaxPooling2D(pool_size=(4,4),name=blockname+'x2_pool')(concate_one)
#     # print('x2pooling.shape{}'.format(x2.shape))
#     x2_upsampled =UpSampling2D(size=2, interpolation='bilinear', name=blockname+'x2_upsampling')(x1)
#     print('x2upsampling.shape{}'.format(x2_upsampled.shape))
#     concate_two=concatenate([concate_one,x2_upsampled,inp])
#     print('x2concateante.shape{}'.format(concate_two.shape))
#     # print('concate_two.shape{}'.format(concate_two.shape))

#     x3=MaxPooling2D(pool_size=(8,8),name=blockname+'x3_pool')(concate_two)
#     print('x3pooling.shape{}'.format(x3.shape))
#     x3_upsampled =UpSampling2D(size=8, interpolation='bilinear', name=blockname+'x3_upsampling')(x3)
#     # print('x3_upsampled{}'.format(x3_upsampled))
#     print('x3upsampling.shape{}'.format(x3_upsampled.shape))
    
#     x4 = GlobalAveragePooling2D(name=blockname+'x3_pooling')(inp)
#     print('x4.shape{}'.format(x4.shape))
#     x4 = Reshape((1,1,feature_width))(x4)
#     print('x4.shape{}'.format(x4.shape))
#     x4 = Convolution2D(filters=feature_width,kernel_size=(1,1),name=blockname+'red_1_by_1')(x4)
#     print('x4.shape{}'.format(x4.shape))
#     x4 = UpSampling2D(size=IMG_SIZE,name=blockname+'red_upsampling')(x4)
#     print('x4upsamping.shape{}'.format(x4.shape))
#     concate_three=concatenate([x1_upsampled,x2_upsampled,x3_upsampled,x4,inp])
#     print('outputcaoncateante.shape{}'.format(concate_three.shape))
#     print('---------------------------------------------')
#     print('x1_upsampled.shape{}'.format(x1_upsampled.shape))
#     print('x2_upsampled.shape{}'.format(x2_upsampled.shape))
#     print('x3_upsampled.shape{}'.format(x3_upsampled.shape))
#     print('x4.shape{}'.format(x4.shape))
#     print('INP.shape{}'.format(inp.shape))
#     # print(concate_three.shape)

#     return concate_three
