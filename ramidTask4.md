# Zero to Hero Həftəsi
# Ramid Askerov

🕒 Deadline:  
![deadline](https://readme-typing-svg.demolab.com?font=Fira+Code&pause=10&color=E63946&center=true&vCenter=true&width=200&fontSize=40&lines=Cümə,+24%3A00)

---

![35cc42f4153ca913095639cb9936cfd8](https://github.com/user-attachments/assets/2d95f03d-9720-4661-830f-d8db16c072e1)



## Task 1 — Xətalı FutureBuilder istifadə

 ❌ Xətalı kod:

Future<String> getData() {
  Future.delayed(Duration(seconds: 2));
  return "Hello";
}

@override
Widget build(BuildContext context) {
  return FutureBuilder(
    future: getData,
    builder: (context, snapshot) {
      if (snapshot.connectionState == ConnectionState.waiting) {
        return CircularProgressIndicator();
      }
      return Text(snapshot.data);
    },
  );
}


# 🧩 Developer tapşırığı: Koddakı 3 xətanı tap və düzəlt.

## Task 2 — Loading vəziyyəti səhv işləyir

 ❌ Xətalı kod:

Future<List<String>> fetchItems() async {
  return Future.delayed(Duration(seconds: 1), () {
    ["Apple", "Orange"];
  });
}

Widget build(context) {
  return FutureBuilder<List<String>>(
    future: fetchItems(),
    builder: (context, snapshot) {
      if (snapshot.hasData == false) {
        return Text("Loaded");
      }
      return ListView(
        children: snapshot.data!.map((e) => Text(e)).toList(),
      );
    },
  );
}


# 🧩 Tapşırıq: Siyahı ekranda görünmür. Xətanı tap.

## Task 3 — API error göstərilmir

 ❌ Xətalı kod:

Future<String> loadUser() async {
  throw Exception("Network Error");
}

Widget build(context) {
  return FutureBuilder<String>(
    future: loadUser(),
    builder: (context, snap) {
      if (snap.connectionState == ConnectionState.done) {
        return Text(snap.data!);
      }
      return Text("Waiting...");
    },
  );
}


# 🧩 Tapşırıq: Xəta baş verəndə ekranda heç nə dəyişmir. Səbəbi tap.

##  Task 4 — Wrong async/await usage

❌ Xətalı kod:

Future<int> calculate() async {
  int x = await Future(() => 5);
  int y = Future(() => 10);
  return x + y;
}


# 🧩 Tapşırıq: Kod niyə işləmir? Problemi göstər.

## Task 5 — Retry düyməsi işləmir

 ❌ Xətalı kod:

late Future<String> future;

@override
void initState() {
  future = loadData();
}

Future<String> loadData() async {
  return Future.delayed(Duration(seconds: 1), () => "OK");
}

Widget build(context) {
  return Column(
    children: [
      FutureBuilder(
        future: future,
        builder: (context, snapshot) {
          return Text(snapshot.data ?? "Loading");
        },
      ),
      ElevatedButton(
        onPressed: () {
          loadData();
        },
        child: Text("Retry"),
      ),
    ],
  );
}


# 🧩 Tapşırıq: Retry düyməsinə basanda UI yenilənmir. Səbəbi tap.

## ✅ Hissə 2 — Normal 5 Task (Xəta yoxdur)
## Task 6

 Future ilə API-dən məlumatı çək, yüklənərkən loading göstər, nəticədə list çıxart.

## Task 7

Pull-to-refresh ilə siyahını yenilə (RefreshIndicator istifadə et).

## Task 8

Future timeout olarsa ekranda “Request Timeout” mesajı göstər.

## Task 9

Future nəticəsi boş siyahı olarsa “No Data Found” widget-ı göstər.

## Task 10

API nəticəsinə görə UI-də 3 vəziyyət göstər:

Loading

Error

Success

#######################################################################################################
# 5 Interview Sualları (Variantlı)

![e3696f7becee98cb580a473f4916b852](https://github.com/user-attachments/assets/e97440b8-2313-4c5b-9dce-07edde7fcac9)


## Sual 1: FutureBuilder nə üçündür?
A) Asinxron əməliyyat nəticəsini UI-də göstərmək
B) UI-də hər zaman statik məlumat göstərmək
C) Animasiya yaratmaq
D) Form məlumatlarını göndərmək

## Sual 2: Future tamamlanana qədər hansı widget istifadə olunur?
A) Text
B) CircularProgressIndicator
C) Icon
D) Container

## Sual 3: API çağırışı uğursuz olarsa nə etmək lazımdır?
A) UI-də xətanı göstərmək
B) Heç nə etməmək
C) Məlumatları silmək
D) Yalnız konsolda yazmaq

## Sual 4: async və await nə üçün istifadə olunur?
A) Kodun daha uzun olmasını təmin etmək
B) Asinxron əməliyyatları daha oxunaqlı etmək
C) UI-ni rəngləndirmək
D) Kodun sürətini artırmaq üçün

## Sual 5: Pull-to-refresh nə üçün istifadə olunur?
A) Məlumatı yeniləmək üçün
B) UI animasiyasını göstərmək üçün
C) Form məlumatlarını göndərmək üçün
D) ListView-də şəkilləri göstərmək üçün
