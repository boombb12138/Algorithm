---
timezone: Asia/Shanghai
---

> 请在上边的 timezone 添加你的当地时区，这会有助于你的打卡状态的自动化更新，如果没有添加，默认为北京时间 UTC+8 时区
> 时区请参考以下列表，请移除 # 以后的内容

timezone: Pacific/Honolulu # 夏威夷-阿留申标准时间 (UTC-10)

timezone: America/Anchorage # 阿拉斯加标准时间 (UTC-9)

timezone: America/Los_Angeles # 太平洋标准时间 (UTC-8)

timezone: America/Denver # 山地标准时间 (UTC-7)

timezone: America/Chicago # 中部标准时间 (UTC-6)

timezone: America/New_York # 东部标准时间 (UTC-5)

timezone: America/Halifax # 大西洋标准时间 (UTC-4)

timezone: America/St_Johns # 纽芬兰标准时间 (UTC-3:30)

timezone: America/Sao_Paulo # 巴西利亚时间 (UTC-3)

timezone: Atlantic/Azores # 亚速尔群岛时间 (UTC-1)

timezone: Europe/London # 格林威治标准时间 (UTC+0)

timezone: Europe/Berlin # 中欧标准时间 (UTC+1)

timezone: Europe/Helsinki # 东欧标准时间 (UTC+2)

timezone: Europe/Moscow # 莫斯科标准时间 (UTC+3)

timezone: Asia/Dubai # 海湾标准时间 (UTC+4)

timezone: Asia/Kolkata # 印度标准时间 (UTC+5:30)

timezone: Asia/Dhaka # 孟加拉国标准时间 (UTC+6)

timezone: Asia/Bangkok # 中南半岛时间 (UTC+7)

timezone: Asia/Shanghai # 中国标准时间 (UTC+8)

timezone: Asia/Tokyo # 日本标准时间 (UTC+9)

timezone: Australia/Sydney # 澳大利亚东部标准时间 (UTC+10)

timezone: Pacific/Auckland # 新西兰标准时间 (UTC+12)

---

# {Naomi}

1. 自我介绍 software engineer
2. 你认为你会完成本次残酷学习吗？yes

## Notes

<!-- Content_START -->

### 2024.10.19

## 4.1 数组

数组（array）是一种线性数据结构，其将相同类型的元素存储在连续的内存空间中

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a6ca9822-e902-41f9-90d9-747f9ae75db0/3b88d720-d90f-4023-8afe-4db617395381/image.png)

### **4.1.1   数组常用操作**

插入元素

```jsx
/* 在数组的索引 index 处插入元素 num */
function insert(nums, num, index) {
    // 把索引 index 以及之后的所有元素向后移动一位
    for (let i = nums.length - 1; i > index; i--) {
        nums[i] = nums[i - 1];
    }
    // 将 num 赋给 index 处的元素
    nums[index] = num;
}
```

删除元素

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a6ca9822-e902-41f9-90d9-747f9ae75db0/c1b0cc21-29e9-42c8-ad73-f352d15b0101/image.png)

```jsx
/* 删除索引 index 处的元素 */
function remove(nums, index) {
    // 把索引 index 之后的所有元素向前移动一位
    for (let i = index; i < nums.length - 1; i++) {
        nums[i] = nums[i + 1];
    }
}
```

查找元素

```jsx
/* 在数组中查找指定元素 */
function find(nums, target) {
    for (let i = 0; i < nums.length; i++) {
        if (nums[i] === target) return i;
    }
    return -1;
}
```

扩展数组

在js中 数组动态的 可直接扩展

数组的典型应用：
• **排序和搜索**：数组是排序和搜索算法最常用的数据结构。快速排序、归并排序、二分查找等都主要在数组上进行。

- [x]  完成了3道数组

### 2024.10.25
https://leetcode.cn/problems/3sum/submissions/575748372/
### 2024.10.26
### 2024.10.27

### 2024.10.28
/**
 * @param {number[]} nums
 * @return {number[]}
 */
var productExceptSelf = function(nums) {
    const len = nums.length;
    if(len==0)return[];//处理边界

const ans = new Array(len).fill(1);//这个数组一开始存放左部分的乘积，后面存放最终的结果
let tmp=1;//这个是用来存放右部分的乘积
 //第一个循环是计算左部分的乘积
 for(let i = 1;i<len;i++){
    ans[i]=ans[i-1]*nums[i-1];
 }
 for(let i =len-2;i>=0;i--){
    tmp*=nums[i+1];//计算右半部分的乘积 所以是i+1
    ans[i] *= tmp;//把左边和右边的相乘就得到了结果
 }
 return ans;
};
### 2024.10.29
### 2024.10.30
https://leetcode.cn/problems/maximum-product-subarray/
```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxProduct = function(nums) {
    let max=-Infinity,imax=1,imin=1;//设置max是-Infinity，这样当imax是负数的时候也能存储在max中
    for(let i =0;i<nums.length;i++){
        //令imax等于当前最大值
  if(nums[i]<0){
       //当nums[i]为负的时候 imax乘以nums[i]反而会变成最小的 所以要将imax和imin交换 再计算最大值和最小值
            let tmp = imax;
            imax = imin;
            imin=tmp;
        }

        // 当nums[i]为正的时候
        imax=Math.max(imax*nums[i],nums[i]);//最大值会等于当前遍历到的值乘以imax
        imin= Math.min(imin*nums[i],nums[i]);
      
      max=Math.max(max,imax);//imax是对于当前遍历到的元素的数组乘积最大值，max存储的是已知的最大值，所以得有max这个变量
    }
    return max
};
```
### 2024.10.31
153. 寻找旋转排序数组中的最小值 - 力扣（LeetCode）
33. Search in Rotated Sorted Array
https://leetcode.cn/problems/search-in-rotated-sorted-array/description/

### 2024.11.02
11. Container With Most Water
https://leetcode.cn/problems/container-with-most-water/
<!-- Content_END -->
