import UIKit

/*1. Описать класс Car c общими свойствами автомобилей и пустым методом действия по аналогии с прошлым заданием.

2. Описать пару его наследников trunkCar и sportСar. Подумать, какими отличительными свойствами обладают эти автомобили. Описать в каждом наследнике специфичные для него свойства.

3. Взять из прошлого урока enum с действиями над автомобилем. Подумать, какие особенные действия имеет trunkCar, а какие – sportCar. Добавить эти действия в перечисление.

4. В каждом подклассе переопределить метод действия с автомобилем в соответствии с его классом.

5. Создать несколько объектов каждого класса. Применить к ним различные действия.

6. Вывести значения свойств экземпляров в консоль.*/

enum CarType {
    case sport
    case truck
}

enum CarAction {
    case someAction
}

class Car {
    
    var wheels: Int
    var type: CarType
    
    init(wheels: Int, type: CarType) {
        self.wheels = wheels
        self.type = type
        }
    
    func handleAction(action: CarAction) {}
}

class Sport: Car {
    
    var cargoSpace: Int
    var seats: Int
    
    init(cargoSpace: Int, seats: Int) {
        self.cargoSpace = cargoSpace
        self.seats = seats
        super.init(wheels: 4, type: .sport)
    }
    
    override func handleAction(action: CarAction) {
        switch action {
        case .someAction:
            print("Action succesfuly handled")
        }
    }
}

let audi = Sport(cargoSpace: 200, seats: 2)
audi.cargoSpace
audi.seats
audi.handleAction(action: .someAction)
