<h1 style="text-align: center;">Leetcode Interview 150 Problem Solved</h1>
<img src="leetcode.jpg" align="center"/>

## 209.Minimum Size Subarray Sum
```c++
    class Solution {
public:
    int minSubArrayLen(int target, vector<int>& arr) {
    int n = arr.size();
	int min_length = n+2,j=0;
	int sum=0;
	for(int i=0;i<n;i++){
		sum+=arr[i];
		while(sum>=target){
			min_length = min(min_length,i-j+1);
			sum-=arr[j];
			j++;
		}
	}
	return min_length==n+2?0:min_length;
    }
};
```