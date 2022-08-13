# leetcode-121

 1) bruce force
 
        def maxProfit(self, prices: List[int]) -> int:
            # maxProfit = 0
            # for i in range(len(prices)-1):
            #     for j in range(i+1, len(prices)):
            #         ans = prices[j]-prices[i]
            #         if ans > maxProfit:
            #             maxProfit = ans    
            # return maxProfit


2) sliding windows:

        def maxProfit(self, prices: List[int]) -> int:
            maxProfit = 0
            l = 0
                 # buy - low
            r = 1
                 # sell - high
            for r in range(len(prices)):
                if prices[l] < prices[r]:
                        # exist profit
                    profit = prices[r] - prices[l]
                    maxProfit = max(maxProfit, profit)
                else:
                    l = r
                        # if prices[l] > prices[r]; r always helps to find the min val.
                        # [7,3,6,1,5,2]
                        #    l   r       r找到了较小的值，l换过来。相当于帮l找最小；然后继续回到上面跑剩余程序——找差值/profit
                        #        l r -  back to "if". so no actions here
            return maxProfit
            
            
            
   sliding windows// stock类似题目：3// 122,123,188, 309,714
