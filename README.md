# project
first project

import UIKit

/*
 1. Описать несколько структур – любой легковой автомобиль SportCar и любой грузовик TrunkCar.
 
 2. Структуры должны содержать марку авто, год выпуска, объем багажника/кузова, запущен ли двигатель, открыты ли окна, заполненный объем багажника.
 
 3. Описать перечисление с возможными действиями с автомобилем: запустить/заглушить двигатель, открыть/закрыть окна, погрузить/выгрузить из кузова/багажника груз определенного объема.
 
 4. Добавить в структуры метод с одним аргументом типа перечисления, который будет менять свойства структуры в зависимости от действия.
 
 5. Инициализировать несколько экземпляров структур. Применить к ним различные действия.
 
 6. Вывести значения свойств экземпляров в консоль.*/

enum Mark {
    case bmw
}
enum EngineState {
    case isOn, isOff
}
enum CarAction {
    case someAction(someValue: Double)
    case setEngineState(EngineState)
}

struct SportCar {
    let mark: Mark
    let year: Int
    var trunkVolume: Double
    var engineState: EngineState // запущен ли двигатель

    mutating func handleAction(action: CarAction) {
        switch action {
        case .setEngineState(let state):
            self.engineState = state
        case .someAction(someValue: let value):
            self.trunkVolume += value
        }
    }
}

var car = SportCar(mark: .bmw, year: 2021, trunkVolume: 180, engineState: .isOff)
car.handleAction(action: .setEngineState(.isOn))
car.handleAction(action: .someAction(someValue: 150))

