# self-dividing-numbers
class Solution(object):
    def selfDividingNumbers(self, left, right):
        """
        :type left: int
        :type right: int
        :rtype: List[int]
        """
        def is_self_dividing(num):
            x = num
            while x > 0:
                digit = x % 10
                if digit == 0 or num % digit != 0:
                    return False
                x //= 10
            return True

        result = []
        for num in range(left, right + 1):
            if is_self_dividing(num):
                result.append(num)

        return result
