# javascript-leetcode
leetcode题解

## 盛最多水的容器
双指针法
面积为 宽 * 高 
宽为两侧索引距离 高为最短木板决定
```javascript
var maxArea = function(height) {
    let max = 0;
    let left = 0; // 左侧木板指针
    let right = height.length -1; //代表右侧木板指针
    while(left<right){
        let current = (right - left) * Math.min(height[left],height[right]) // 当前木板的 距离 * 最小高度即为面积 
        max = Math.max(current,max) // 更新目前的最大面积 
        height[left] < height[right] ? left++ : right--; 
    }
    return max
};
```

## 数组中重复的数字
```javascript
var findRepeatNumber = function(nums) {
    let map = new Map();
    let result = 0;
    for(let i =0;i<nums.length;i++){
        if(map.has(nums[i])){
            result = nums[i];
            break;
        }
        else{
            map.set(nums[i],nums[i])
        }
    }
    return result
};
```
