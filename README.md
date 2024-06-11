#  prominence 参数
# 1、找到峰值左右两侧的最低点(谷值)。2、计算峰值到左右两侧谷值的垂直距离。3、取这两个垂直距离的较小值,就得到了这个峰值的显著性。


# 使用scipy.signal.find_peaks进行峰检测
# height: 峰值必须超过此阈值才能被认为是峰
# distance: 峰之间的最小距离
peaks, properties = scipy.signal.find_peaks(X_sample, height=20, distance=50, prominence=0.6)  # 假设最小峰间距为50
![image](https://github.com/avaping/avaping/assets/147402275/1fc1cbbf-9fd0-4f8a-932b-dfa32b67dd8a)

# 横坐标从24000变成了80，意味着一个坐标间隔包含300个数据点，根据初次调试的参数，根据参数原理进行调参
# 观察到，虽然基线处于22.5左右，但height值不敏感。先调 prominence
peaks, properties = scipy.signal.find_peaks(X_sample, height=20, distance=50, prominence=0.2)  # 假设最小峰间距为50
![image](https://github.com/avaping/avaping/assets/147402275/f0e9dd7d-4e27-4801-8059-b6bb5c19eef9)

# 再调distance参数
peaks, properties = scipy.signal.find_peaks(X_sample, height=20, distance=25, prominence=0.2)  # 假设最小峰间距为50
![image](https://github.com/avaping/avaping/assets/147402275/b0566818-4086-4c5b-8444-8781a81f83ea)

# perfect
