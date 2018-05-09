# imgtool
简单图片瘦身和拼接小工具

# 使用

## 图片信息
```
imgtool info test.jpg
```

## 转换格式
```
imgtool conv -f png [-o test-conv.png] test.jpg
```

## 瘦身
```
imgtool slim [-f jpg] [-o test-slim.jpg] test.jpg 
```

## 拼接
水平方向拼接，将N 张图片水平拼接到一起
```
imgtool plus [-f jpg] [-direct 0] [-o test1-testN.jpg] test1.jpg test2.jpg ... testN.jpg 
```

垂直方向拼接，将N 张图片垂直拼接到一起
```
imgtool plus [-f jpg] -direct 1 [-o test1-testN.jpg] test1.jpg test2.jpg ... testN.jpg
```

## Unix 管道和批量操作
批量转换格式
```
find . -name "*.jpg" | xargs -I{} imgtool conv -f png {}
```

批量图片水平拼接
```
find . -name "*.jpg" | sort | imgtool plus -o plus.jpg
```