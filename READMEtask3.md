# 1. Basic Future

Future.delayed istifadə edərək 3 saniyə sonra ekrana “Hello Flutter” yazan bir proqram yazın.

# 2. Async Function

async funksiyası yaradın ki, 2 saniyə gözləsin və sonra bir int qaytarsın (məsələn, 50).

# 3. Future.then()

Future istifadə edərək .then() ilə 1 saniyə sonra “Future tamamlandı” yazdırın.

# 4. Error Handling

Bir Future yaradın ki, bəzən error atsın (throw Exception). try/catch və ya .catchError() istifadə edərək erroru konsola çıxarın.

# 5. Future with Return Value

Future yaradın ki, iki ədədin cəmini hesablasın və nəticəni konsola yazdırsın.

# 6. Multiple Futures

3 Future yaradın: biri 1 saniyə, biri 2 saniyə, biri 3 saniyə sonra tamamlanır. Future.wait istifadə edərək bütün nəticələri eyni anda konsola çıxarın.

# 7. Sequential Futures

İki Future yaradın:

- Birincisi 2 saniyə gözləsin və “Step 1” qaytarsın.
- İkincisi 1 saniyə gözləsin və “Step 2” qaytarsın.

Nəticələri ardıcıl olaraq konsola yazın.

# 8. Future with List

Future yaradın ki, 2 saniyə sonra bir list qaytarsın: ["Ali", "Veli", "Ayşe"]. Listi konsola çıxarın.

# 9. Chained Futures

Bir Future yaradın ki, daxil edilmiş ədədi 2 ilə vurub qaytarsın. Sonra .then() ilə nəticəni bir daha 2 ilə vurub yekun nəticəni konsola yazın.

# 10. Future with Conditional Result

Future yaradın ki, daxil edilmiş ədəd 10-dan böyükdürsə “Big number”, kiçikdirsə error atsın. Erroru try/catch ilə konsola yazdırın.
