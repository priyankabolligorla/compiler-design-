#include <stdio.h>

// Structure to represent an expression
struct Expression {
    char op;             // Operator: +, -, *, /
    int leftOperand;
    int rightOperand;
    int result;          // Result of the expression
};

// Function to evaluate an expression
int evaluateExpression(struct Expression* expr) {
    switch (expr->op) {
        case '+':
            return expr->leftOperand + expr->rightOperand;
        case '-':
            return expr->leftOperand - expr->rightOperand;
        case '*':
            return expr->leftOperand * expr->rightOperand;
        case '/':
            return expr->leftOperand / expr->rightOperand;
    }
    return 0; // Invalid operator
}

// Function to eliminate common subexpressions
void eliminateCommonSubexpressions(struct Expression* expr1, struct Expression* expr2) {
    if (expr1->op == expr2->op &&
        expr1->leftOperand == expr2->leftOperand &&
        expr1->rightOperand == expr2->rightOperand) {
        // The expressions are the same, reuse the result
        expr2->result = expr1->result;
    }
}

int main() {
    struct Expression expr1 = {'+', 5, 3, 0}; // 5 + 3
    struct Expression expr2 = {'*', 5, 3, 0}; // 5 * 3

    // Evaluate the expressions
    expr1.result = evaluateExpression(&expr1);
    expr2.result = evaluateExpression(&expr2);

    // Perform common subexpression elimination
    eliminateCommonSubexpressions(&expr1, &expr2);

    // Print results
    printf("Expression 1 result: %d\n", expr1.result);
    printf("Expression 2 result: %d\n", expr2.result);

    return 0;
}
