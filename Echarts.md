# 1.雷达图刻度只显示顶部的线上
```
axisLabel: {show: true,
            showMinLabel: false,
            showMaxLabel: false,
            formatter (value, index) {
              if (index === 0 && sign === undefined) {
                sign = true
                return value
              }
              if (index > 0 && sign) {
                return value
              }
              if (index === 0 && sign) {
                sign = false
              }
            }}
```
