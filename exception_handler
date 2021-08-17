# Then in your main file reassign excepthook function in sys module to handle_exception by doing:
# sys.excepthook = handle_exception

import random as rd
import traceback


# This is function responsible for an error message generation. You can use your own depending on your goals and needs.
# This one just adds random phrases predefined in ...PHRASES-arrays to an initial error message
# If an error was "IndexError: list index out of range",
# generate_str function would only get "list index out of range" and return something like "oh man list index out of range u silly goose"

def generate_str(s):
    PHRASES = []  # added both at the beginning and at the end
    FIRST_PHRASES = []  # added only at the beginning
    SECOND_PHRASES = []  # added only at the end. each phrase begins with '\n' symbol
    
    first = rd.choice(PHRASES + FIRST_PHRASES + [''])
    second = rd.choice([i for i in PHRASES if not first or i != first and first[0] != i[0]] + SECOND_PHRASES + [''])  # so that additionnal messages don't repeat themselves
    first = first + ' ' if first else first
    second = ' ' + second if second and second[0] != '\n' else second
    return first + s + second


def handle_exception(type, value, tb):
    value = type(generate_str(str(value)))
    traceback.print_exception(type, value, tb)

