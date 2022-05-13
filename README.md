# Problem Solution:
  Two Sum
# Difficulty:
  Easy
# Description:
  Given an array of integers nums and an integer target, return indices of the two numbers such    that they add up to target.
  Example:
  Input: nums = [2,7,11,15], target = 9
  Output: [0,1]
  For more details: https://leetcode.com/problems/two-sum/
# Idea:
  - Using Hash Map to store value and index of nums[i] in given array:
    - Key = nums[i];
    - Value = i;
  - Get to the next element.
  - Once encounter 'target-nums[i]' in hash map, we push 'i' and 'map[target-nums[i]]' (index of 'target-nums[i]') into 'Result'.
# Code:
  Here is my completed function:
  
    vector<int> twoSum(vector<int>& nums, int target) {
        map <int,int> hashMap;
        int n = nums.size();
        vector<int> result;
        for(int i=0;i<n;++i){
            if(hashMap.find(target-nums[i])==hashMap.end()){
               hashMap[nums[i]]=i;
            }
            else{
                result.push_back(i);
                result.push_back(hashMap[target-nums[i]]);
            }
        }
        return result;
    }
