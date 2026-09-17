@startuml
title Laundry Room Booking System - First Domain Model

class Tenant
class PropertyManager
class MaintenanceTechnician
class HousingCompany
class ApartmentBuilding
class LaundryRoom
class Machine
class WashingMachine
class Dryer
class Reservation
class TimeSlot
class FaultReport
class Maintenance
class MaintenanceSchedule
class MaintenanceHistory
class AccessPermission
class AccessAttempt
class Notification

HousingCompany "1" -- "*" ApartmentBuilding : manages
ApartmentBuilding "1" -- "*" Tenant : houses
ApartmentBuilding "*" -- "*" LaundryRoom : has access to

LaundryRoom "1" -- "*" Machine : contains

Machine <|-- WashingMachine
Machine <|-- Dryer

Tenant "1" -- "*" Reservation : makes
LaundryRoom "1" -- "*" Reservation : reserved through
Reservation "1" -- "1" TimeSlot : uses

Tenant "1" -- "*" FaultReport : creates
Machine "0..1" -- "*" FaultReport : concerns
LaundryRoom "0..1" -- "*" FaultReport : concerns

PropertyManager "1" -- "*" MaintenanceSchedule : manages
MaintenanceSchedule "*" -- "0..1" Machine : concerns
MaintenanceSchedule "*" -- "0..1" LaundryRoom : concerns

MaintenanceTechnician "1" -- "*" Maintenance : performs
Machine "0..1" -- "*" Maintenance : receives
LaundryRoom "0..1" -- "*" Maintenance : receives
MaintenanceHistory "1" -- "*" Maintenance : contains

Reservation "1" -- "0..1" AccessPermission : provides
Tenant "1" -- "*" AccessAttempt : makes
LaundryRoom "1" -- "*" AccessAttempt : receives

Tenant "1" -- "*" Notification : receives
Reservation "0..1" -- "*" Notification : concerns

@enduml
