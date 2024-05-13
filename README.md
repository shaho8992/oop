def full_adder(a, b, carry_in):
    sum_bit = a ^ b ^ carry_in
    carry_out = (a & b) | (carry_in & (a ^ b))
    return sum_bit, carry_out

a, b, carry_out = 1, 1, 1

sum_bit, carry_out = full_adder(a, b, carry_in)

print("sum :", sum_bit)
print("carry_out :", carry_out)

\\\\\\\\\\\\\\\\\\\\\\
def full_subtract(a, b, borrow_in):
    diff_bit = a ^ b ^ borrow_in
    borrow_out = ((~a) & b) | ((~a) & borrow_in) | (b & borrow_in)
    return diff_bit, borrow_out
a, b, borrow_in = 1, 1, 1

diff_bit, borrow_out =  full_subtract(a, b, borrow_in)

print("diffrence :", diff_bit)
print("borrow_out :", borrow_out)
