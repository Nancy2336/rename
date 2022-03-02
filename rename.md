# -*- coding:utf8 -*-
 
import os
 
class BatchRename():
    
    def __init__(self):
        self.path='C:\\Users\\Administrator\\test' #选择要修改图片格式的文件夹
    def rename(self):
        filelist = os.listdir(self.path) #获取文件路径
        total_num = len(filelist) #获取文件长度（个数）
        i = 1 #表示文件的命名是从1开始的
        for item in filelist:
            if item.endswith(('.jpg','.png','.jpeg','.bmp','.JPG','PNG')): #初始的图片的格式为jpg格式的（或者源文件是png格式及其他格式，后面的转换格式就可以调整为自己需要的格式即可）
                src = os.path.join(os.path.abspath(self.path), item)
                dst = os.path.join(os.path.abspath(self.path), str(i) + '.jpg')#处理后的格式也为jpg格式的，当然这里可以改成png格式
            try:
                os.rename(src, dst)
                print ('converting %s to %s ...' % (src, dst))
                i = i + 1
            except:
                continue
        print('total %d to renamestrat & converted %d jpgs' % (total_num, i))
 
if __name__ == '__main__':
    
    demo = BatchRename()
    demo.rename()
