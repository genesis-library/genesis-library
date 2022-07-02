https://www.typescriptlang.org/docs/handbook/type-compatibility.html
https://stackoverflow.com/questions/14311675/typescript-declaration-files-contain-class-definitions-with-no-member-implementa/14323673#14323673

```
const validation = checkUpdateFormValidation({  
  newName: updatedAdvertInfo.name,  
  newAmount: updatedAdvertInfo.budgetAmount,  
  newEndDate: updatedAdvertInfo.endDate!,  
  amount: Number(advert.budget.totalAmount),  
  endDate: advert.endDate,  
  formatMessage,  
}: FormValidationInputs);

function invocation?
function call esnasında tip veremiyor muyum?
```