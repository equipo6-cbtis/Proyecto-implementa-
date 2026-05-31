# Proyecto-implementa-
inventario = []

while True:
    print("\n===== FARMACIA =====")
    print("1. Agregar medicamento")
    print("2. Mostrar inventario")
    print("3. Buscar medicamento")
    print("4. Actualizar stock")
    print("5. Eliminar medicamento")
    print("6. Salir")

    opcion = input("Seleccione una opción: ")

    # Agregar medicamento
    if opcion == "1":
        nombre = input("Nombre del medicamento:")
        precio = float(input("Precio: $"))
        stock = int(input("Cantidad en existencia:"))

        medicamento = {
            "nombre": nombre,
            "precio": precio,
            "stock": stock
        }

        inventario.append(medicamento)
        print("Medicamento agregado correctamente.")

    # Mostrar inventario
    elif opcion == "2":
        if len(inventario) == 0:
            print("No hay medicamentos registrados.")
        else:
            print("\n--- INVENTARIO ---")
            for med in inventario:
                print(f"Nombre: {med['nombre']}")
                print(f"Precio: ${med['precio']:.2f}")
                print(f"Stock: {med['stock']}")
                print("-------------------")

    # Buscar medicamento
    elif opcion == "3":
        buscar = input("Ingrese el nombre del medicamento:")
        encontrado = False

        for med in inventario:
            if med["nombre"].lower() == buscar.lower():
                print("\nMedicamento encontrado")
                print(f"Nombre: {med['nombre']}")
                print(f"Precio: ${med['precio']:.2f}")
                print(f"Stock: {med['stock']}")
                encontrado = True
                break

        if not encontrado:
            print("Medicamento no encontrado.")

    # Actualizar stock
    elif opcion == "4":
        nombre = input("Nombre del medicamento: ")

        for med in inventario:
            if med["nombre"].lower() == nombre.lower():
                nuevo_stock = int(input("Nuevo stock: "))
                med["stock"] = nuevo_stock
                print("Stock actualizado correctamente.")
                break
        else:
            print("Medicamento no encontrado.")

    # Eliminar medicamento
    elif opcion == "5":
        nombre = input("Nombre del medicamento a eliminar: ")

        for med in inventario:
            if med["nombre"].lower() == nombre.lower():
                inventario.remove(med)
                print("Medicamento eliminado.")
                break
        else:
            print("Medicamento no encontrado.")

    # Salir
    elif opcion == "6":
        print("Saliendo del sistema...")
        break

    else:
        print("Opción no válida.")
