# project
first project

import UIKit

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

