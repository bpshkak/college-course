void main() {
  //задание1
  print('===MINI GAME===');

  String heroname = 'Waka';
  int herohealth = 100;
  int heroattack = 20;
  int potions = 2;

  print('Информация героя');
  print('имя: $heroname');
  print('здоровье: $herohealth HP');
  print('сила игрока: $heroattack');
  print('зелий: $potions');

  //задание2
  List<String> enemynames = ['слизень', 'скелет', 'дракон'];
  List<int> enemyhealth = [30, 40, 50];
  List<int> enemypower = [10, 15, 20];

  int defeated = 0;

  List<String> moves = ['abc', '1', '1', '1', '1', '1', '2', '2', '2', '1', '1'];
  int moveIndex = 0;

  for (int i = 0; i < enemynames.length; i++) {
    String enemyname = enemynames[i];
    int currentenemyhealth = enemyhealth[i];
    int power = enemypower[i];

    print('');
    print('--- Противник: $enemyname ---');

    //задание3
    while (currentenemyhealth > 0 && herohealth > 0) {
      print('');
      print('Противник: $enemyname');
      print('Здоровье героя: $herohealth');
      print('Здоровье противника: $currentenemyhealth');
      print('Зелий: $potions');
      print('1 - Атаковать, 2 - Зелье');

      String choice = moves[moveIndex];
      moveIndex++;
      print('Выбор: $choice');

      if (choice == '1') {
        currentenemyhealth -= heroattack;
        print('атакуэйшн');
      } else if (choice == '2') {
        if (potions == 0) {
          print('зелий больше нет');
          continue;
        }
        herohealth += 30;
        if (herohealth > 100) {
          herohealth = 100;
        }
        potions--;
        print('выпил зелье');
      } else {
        print('неверный ввод');
        continue;
      }

      if (currentenemyhealth > 0) {
        herohealth -= power;
        print('$enemyname атакует');
      }
    }

    //задание4
    if (herohealth <= 0) {
      print('игра салам');
      return;
    }

    defeated++;
    print('победил $enemyname');
  }

  print('');
  print('поздравляем! победил!');
  print('Имя героя: $heroname');
  print('Побеждено противников: $defeated');
  print('Оставшееся здоровье: $herohealth');
}
