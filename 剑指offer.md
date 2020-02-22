# 剑指offer
## 项目背景
本项目是 学习剑指offer电子书以及在leetcode中刷配套试题 的 学习记录和总结

## 剑指offer电子书梳理
大致浏览了一遍，觉得还是先刷题，然后再去看对应的章节比较好      
我的电子书为第一版，leetcode中为第二版，下面的记录以leetcode中的第二版为准。      
以下代码使用JavaScript编写     
### 面试题03 数组中重复的数字
1. 遍历数组，用另一个数组来存储遍历过的数字
      /**
      * @param {number[]} nums
      * @return {number}
      */
      var findRepeatNumber = function(nums) {
        let map = [];
        for(let i = 0; i < nums.length; i ++){
          if(map[nums[i]]){
            return nums[i];
          }else{{
            map[nums[i]] = 1;
          }}
        }
      };
### 面试题04 二维数组中的查找
1. 暴力法 O(mn)
2. 线性查找 O(m+n)
      /**
      * @param {number[][]} matrix
      * @param {number} target
      * @return {boolean}
      */
      var findNumberIn2DArray = function(matrix, target) { 
        // // O(nm)
        // for(let i = 0; i < matrix.length; i ++){
        //   for(let j = 0; j < matrix[i].length; j ++){
        //     if(matrix[i][j] == target){
        //       return true;
        //     }
        //   }
        // }
        // return false;

        // 线性查找 O(n+m)
        // 从右上角开始查找，当前数小于target往下移(因为当前数是这一行中最大的数)，大于target往左移（因为当前数是该列中最小的数）
        if(matrix.length == 0){
          return false;
        }
        let i = 0;
        let j = matrix[0].length-1;
        while(i<=matrix.length-1 && j>=0){
          console.log(matrix[i][j])
          if(matrix[i][j] < target){
            i ++;
          }else if(matrix[i][j] > target){
            j --;
          }else{
            return true;
          }
        }
        return false;
      };
### 面试题05 替换空格
1. 额外的空间来存储新的字符串
2. String.substring()
3. Srting.split()和Array.join()
4. Srting.split()、Array.splice()、Array.join()

      /**
      * @param {string} s
      * @return {string}
      */
      var replaceSpace = function(s) {
        // 额外的空间
        let res = "";
        for(let i = 0; i < s.length; i ++){
          if(s[i] == " "){
            res += "%20";
          }else{
            res += s[i];
          }
        }
        return res;

        // // String.substring()
        // for(let i = 0; i < s.length; i ++){
        //   if(s[i] == " "){
        //     s = s.substring(0,i) + "%20" + s.substring(i+1,s.length);
        //   }
        // }
        // return s;

        // // Srting.split()和Array.join()
        // let arr = s.split(" ");
        // return arr.join("%20");

        // Srting.split()、Array.splice()、Array.join()
        // let arr = s.split("");
        // for(let i = 0; i < arr.length; i ++){
        //   if(arr[i] == " "){
        //     arr.splice(i,1,"%20");
        //   }
        // }
        // return arr.join("");

      };

### 面试题06 从尾到头打印链表
1. Array.reverse()
2. 递归法
3. 辅助栈法
      /**
      * Definition for singly-linked list.
      * function ListNode(val) {
      *     this.val = val;
      *     this.next = null;
      * }
      */
      /**
      * @param {ListNode} head
      * @return {number[]}
      */
      var reversePrint = function(head) {
        // // Array.reverse()
        // let res = [];
        // while(head != null){
        //   res.push(head.val);
        //   head = head.next;
        // }
        // res.reverse();
        // return res;

        // // 递归法
        // let res = [];
        // let rec = function(head){
        //   if(head != null){
        //     rec(head.next);
        //     res.push(head.val);
        //   }
        // }
        // rec(head);
        // return res;

        // 辅助栈法
        let res = [];
        let stack = [];
        while(head != null){
          stack.push(head.val);
          head = head.next;
        }
        while(stack.length != 0){
          res.push(stack.pop());
        }
        return res;
      };

### 面试题07 重建二叉树

### 面试题09 用两个栈实现队列
### 面试题10-1 斐波那契数列
### 面试题10-2 青蛙跳台阶
### 面试题11 旋转数组的最小数字
### 面试题12 矩阵中的路径
### 面试题13 机器人的运动范围
### 面试题14-1 剪绳子
### 面试题14-2 剪绳子2
### 面试题15 二进制中1的个数
