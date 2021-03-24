def multi(num1, num2):
    n = min(len(str(num1)), len(str(num2)))
    
    if n == 1:
        return num1 * num2 
    divide = n//2
    tens = 10 ** divide
    a = num1 // tens
    b = num1 % tens
    c = num2 // tens
    d = num2 % tens
    
    ac = multi(a, c)
    bd = multi(b, d)
    e = multi(a + b, c + d)

    return (ac * pow(tens, 2)) + bd + \
        ((e - ac - bd) * tens)



num1 = 3141592653589793238462643383279502884197169399375105820974944592
num2 = 2718281828459045235360287471352662497757247093699959574966967627


result = multi(int(num1), int(num2))
print(result)


