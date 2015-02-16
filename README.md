# Prueba.Net
Prueba .Net para optar al cargo de desarrollador Junior - Codetag

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
using System.IO;


namespace WindowsFormsApplication1
{
    public partial class Form1 : Form
        
        
        
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            OpenFileDialog openFileDialog1 = new OpenFileDialog();
            openFileDialog1.Filter = "Archivos txt|*.txt";
            openFileDialog1.FileName = "Seleccione un archivo de Texto";
            openFileDialog1.Title = "Seleccionar archivo .txt";
            openFileDialog1.InitialDirectory = "C:\\";
            openFileDialog1.FileName = this.textBox1.Text;
            if (openFileDialog1.ShowDialog() == DialogResult.OK)
            {
                this.textBox1.Text = openFileDialog1.FileName;
            }

            

        }

        private void button2_Click(object sender, EventArgs e)
            
        {
           
            
            System.IO.StreamReader sr = new System.IO.StreamReader(@textBox1.Text, System.Text.Encoding.Default);
            string texto;
            string salida1 = null;
            string salida2 = null;
            string salida3 = null;
            string salida4 = null;
            while (sr.Peek() >= 0)
            {
                texto = sr.ReadLine();

                char[] matriz = texto.ToCharArray(0,2);
                char[] matriz2 = texto.ToCharArray(2,2);
                char[] matriz3 = texto.ToCharArray(4,2);
                char[] matriz4 = texto.ToCharArray(6,2);
                              
                for (int i = 0; i < matriz.Length; i++)
                {
                    char caracter = matriz[i];
                    salida1 = salida1 + caracter;
                }
                for (int i = 0; i < matriz2.Length; i++)
                {
                    
                    char caracter = matriz2[i];
                    salida2 = salida2 + caracter;
               
                }
                for (int i = 0; i < matriz3.Length; i++)
                {
                    char caracter = matriz3[i];
                    salida3 = salida3 + caracter;

                }
                for (int i = 0; i < matriz4.Length; i++)
                {
                    char caracter = matriz4[i];
                    salida4 = salida4 + caracter;

                }
           
        }
            listBox1.Items.Add(salida1);
            listBox1.Items.Add(salida2);
            listBox1.Items.Add(salida3);
            listBox1.Items.Add(salida4);
            sr.Close();
  
        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }
    
}
}
