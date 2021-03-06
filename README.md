# dklearn
> A Deno Machine Learning Framework


# Usage
## Linear Regression

```typescript
import { LinearRegression, AdvertisingDataLoader } from 'https://deno.land/x/dklearn@0.0.1/mod.ts';

export const runAdvertisingExample = async () => {
    const adData = new AdvertisingDataLoader()
    let [X_train, y_train] = await adData.loadTrain();
    const linReg = new LinearRegression()
    let [WOptimized, BOptimized] = linReg.train(X_train, y_train, 15000, 0, 0, 0.001, true)
    console.log('----------- Training Completed--------------')
    console.log(`Optimized W: ${WOptimized} and Optimized B: ${BOptimized}`);
    let radioExpense = 23.0
    const predictedSales = linReg.predict(radioExpense, WOptimized, BOptimized);
    console.log(`Possible Sales: ${predictedSales}`)
}

runAdvertisingExample()
```