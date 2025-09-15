# -Aplicaci-n-GUI
Este proyecto consiste en una aplicación de interfaz gráfica de usuario (GUI) desarrollada en Python utilizando la librería Tkinter. La aplicación permite al usuario:
import tkinter as tk
from tkinter import messagebox

# Función para agregar un dato a la lista
def agregar():
    dato = entrada.get()  # obtiene el texto del campo
    if dato.strip() != "":  # valida que no esté vacío
        lista.insert(tk.END, dato)  # agrega a la lista
        entrada.delete(0, tk.END)   # limpia el campo de texto
    else:
        messagebox.showwarning("Atención", "Debe ingresar un dato.")

# Función para limpiar la lista
def limpiar():
    lista.delete(0, tk.END)

# Crear ventana principal
ventana = tk.Tk()
ventana.title("Aplicación GUI Básica - Lista de Datos")
ventana.geometry("400x400")  # tamaño de la ventana

# Etiqueta de título
titulo = tk.Label(ventana, text="Gestor de Información", font=("Arial", 14, "bold"))
titulo.pack(pady=10)

# Etiqueta para campo de entrada
lbl = tk.Label(ventana, text="Ingrese un dato:")
lbl.pack()

# Campo de texto
entrada = tk.Entry(ventana, width=30)
entrada.pack(pady=5)

# Botón para agregar
btn_agregar = tk.Button(ventana, text="Agregar", command=agregar, bg="lightgreen")
btn_agregar.pack(pady=5)

# Lista para mostrar los datos
lista = tk.Listbox(ventana, width=40, height=10)
lista.pack(pady=10)

# Botón para limpiar lista
btn_limpiar = tk.Button(ventana, text="Limpiar lista", command=limpiar, bg="lightcoral")
btn_limpiar.pack(pady=5)

# Ejecutar la aplicación
ventana.mainloop()
