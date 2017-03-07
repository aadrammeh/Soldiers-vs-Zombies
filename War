// Amadou Drammeh
// My first program

#include <iostream>
#include <random>
#include <ctime>

using namespace std;

int main()
{
	default_random_engine randomEngine(time(NULL));
	uniform_real_distribution<float> attack(0.0f, 1.0f);

	// Soldiers properties
	float soldierAttack = 0.6f;
	float soldierHealth = 250.0f;
	float soldierDamage = 200.0f;
	float currentSoldierHealth = soldierHealth;

	//Zombie properties
	float zombieAttack = 0.4f;
	float zombieHealth = 50.0f;
	float zombieDamage = 40.0f;
	float currentZombieHealth = zombieHealth;

	float attackResult;

	int startZombies;
	int startSoldiers;

	int numZombies;
	int numSoldiers;

	char turn = 'S';

	cout << " Soldiers Vs Zombies! \n\n";

	//Number of soldiers
	cout << "Enter number of soldiers: ";
	cin >> numSoldiers;

	startSoldiers = numSoldiers;

	//Number of zombies
	cout << "Enter number of zombies: ";
	cin >> numZombies;

	startZombies = numZombies;

	cout << "\nBeginning combat!\n\n";

	while ((numSoldiers > 0) && (numZombies > 0)) {
		
		//Attack result
		attackResult = attack(randomEngine);

		// Soldiers turn
		if (turn == 'S') {

			//if attack was successful
			if (attackResult <= soldierAttack) {
				currentZombieHealth -= soldierDamage;

				if (currentZombieHealth < 0) {
					numZombies--;
					currentZombieHealth = zombieHealth;
				}
			}
			//Zombies turn!
			turn = 'Z';

		}
		else { // if not Soldiers turn, then its Zombies turn!

			if (attackResult <= zombieAttack) {
				currentSoldierHealth -= zombieDamage;

				if (currentSoldierHealth < 0) {
					numSoldiers--;
					currentSoldierHealth = soldierHealth;
				}
			}
			//now its soldiers turn!
			turn = 'S';

		}

	}

	cout << "\nWar is over!\n\n";

	//show results!
	if (numSoldiers > 0) {
		cout << "Soldiers won!\n";
		cout << "There are " << numSoldiers << " soldiers left!\n";
	}
	else {
		cout << "Zombies won!\n";
		cout << "There are " << numZombies << " zombies left!\n";
	}

	//Final result!
	cout << startSoldiers - numSoldiers << " soldiers and " << startZombies - numZombies << " zombies lost their lives.\n\n";

	cout << "Amadou Drammeh" << endl;

	system("PAUSE");
	return 0;
}
