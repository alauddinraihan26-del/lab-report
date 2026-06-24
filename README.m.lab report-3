#include<bits/stdc++.h>
using namespace std;

struct Item {
    int profit;
    int weight;
};


bool compare(const Item &a, const Item &b) {
    double r1 = (double)a.profit / a.weight;
    double r2 = (double)b.profit / b.weight;
    return r1 > r2;
}

double fractionalKnapsack(int capacity, vector<Item> &items) {
    sort(items.begin(), items.end(), compare);

    double totalProfit = 0.0;
    int remaining = capacity;

    for (auto &item : items) {
        if (remaining <= 0)
            break;

        if (item.weight <= remaining) {
            totalProfit += item.profit;
            remaining -= item.weight;
        } else {
           
            double fraction = (double)remaining / item.weight;
            totalProfit += item.profit * fraction;
            remaining = 0;
        }
    }

    return totalProfit;
}

int main() {
    int n, capacity;

    cout << "Enter number of items: ";
    cin >> n;

    vector<Item> items(n);
    cout << "Enter profit and weight for each item:\n";
    for (int i = 0; i < n; i++) {
        cin >> items[i].profit >> items[i].weight;
    }

    cout << "Enter knapsack capacity: ";
    cin >> capacity;

    double maxProfit = fractionalKnapsack(capacity, items);

    cout << "Maximum profit obtainable: " << maxProfit << endl;

    return 0;
}
