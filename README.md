# Leet-code
189,268
189:
class Solution {
public:
    void rotate(vector<int>& nums, int k)
    {
        k=k%nums.size();//k>数组长度的情况
        for(int i=0;i<k;i++)
       {
        int tmp=nums[nums.size()-1];
        
        for(int j=nums.size()-1;j>0;j--)
        {
            nums[j]=nums[j-1];
        }
        nums[0]=tmp;
    }
        std::cout<<'[';
        for(int i=0;i<nums.size()-1;i++)
        {
            std::cout<<nums[i]<<",";
        }
        std::cout<<nums[nums.size()-1]<<"]";
    }
    
};
268:
class Solution {
public:
int missingNumber(vector<int>& nums)
 {
 for (int i = 0; i < nums.size(); i++)
 {
for (int j = i + 1; j < nums.size(); j++)
{
 if (nums[i] > nums[j])
 {
int temp = nums[i];
nums[i] = nums[j];
nums[j] = temp;
  }
}
}
int i=0;
int n=0,sum=0;
int s;
for(i=0;nums[i]!=0;i++)
{
n++;
sum=sum+nums[i];
}
s=(n+1)/2*(nums[0]+nums[n-1]);
return s-sum;
   
}
};
