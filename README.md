// gfg today potd date 19 july 2024
// finding missing in the second array

// java

class Solution
{
   ArrayList<Integer>  findMissing(int a[], int b[],  int N, int M){ 
       
        Set<Integer> s = new HashSet<Integer>();
        ArrayList<Integer> ans = new ArrayList<Integer>();
        for (int i = 0; i < M; i++) 
            s.add(b[i]); 
      
        for (int i = 0; i < N; i++) 
            if (!s.contains(a[i])) 
                ans.add(a[i]);
        return ans;
    } 

}

// c++
  class Solution{
		public:
         vector<int> findMissing(int a[], int b[],  
                 int n, int m) 
	  { 
	      
	    unordered_set <int> s;
	    vector<int> ans;
	    for (int i = 0; i < m; i++) 
	        s.insert(b[i]); 
	  
	    for (int i = 0; i < n; i++) 
	        if (s.find(a[i]) == s.end()) 
	            ans.push_back(a[i]);
	    return ans;
	} 
};

// python 3 code

class Solution:
    def findMissing(self,A,B,N,M):
        s=set()
        ans=[]
        for i in B:
            s.add(i) 
    
        for i in A:
            if i not in s: 
                ans.append(i)
        return ans
