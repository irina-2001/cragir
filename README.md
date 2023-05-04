# cragir
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
namespace Diplomayin_Irina
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
            this.BackColor = Color.DarkBlue;
        }
        private void Form1_Load(object sender, EventArgs e)
        {
            timer1.Enabled = true;
        }
        private void timer1_Tick(object sender, EventArgs e)
        {
            pictureBox1.Top = 168;
            pictureBox1.Left = 31;
            pictureBox1.Width = 225;
            pictureBox1.Height = 130;
            pictureBox2.Top = 670;
            pictureBox2.Left = 1150;
            pictureBox2.Width = 125;
            pictureBox2.Height = 90;          
            Graphics g = this.CreateGraphics();
            g.DrawString("Վանաձորի Հ. Թումանյանի անվան պետական համալսարան", new Font("", 25, FontStyle.Bold), new SolidBrush(Color.White), 180, 10);
            g.DrawString("Մաթեմատիկայի և ինֆորմատիկայի ամբիոն", new Font("", 20, FontStyle.Bold | FontStyle.Italic), new SolidBrush(Color.White), 367, 80);
            g.DrawLine(new Pen(Color.LightBlue, 5), 30, 150, 1400, 150);
            g.DrawString("ԱՎԱՐՏԱԿԱՆ ԱՇԽԱՏԱՆՔ", new Font("", 40, FontStyle.Bold), new SolidBrush(Color.Yellow), 330, 190);
            g.DrawString("Թեմա ՝    Գծային ծրագրավորման խնդիրների լուծումը", new Font("", 30, FontStyle.Bold | FontStyle.Italic), new SolidBrush(Color.White), 50, 320);
            g.DrawString("             սիմպլեքս աղյուսակի միջոցով", new Font("", 30, FontStyle.Bold | FontStyle.Italic), new SolidBrush(Color.White), 220, 370);
            g.DrawString("Ուսանողուհի՝  Թորոսյան Իրինա", new Font("", 25, FontStyle.Bold | FontStyle.Italic), new SolidBrush(Color.Yellow), 50, 550);
           // g.DrawString("Բաժին՝  ԻԿՄ", new Font("", 25, FontStyle.Bold | FontStyle.Italic), new SolidBrush(Color.Yellow), 50, 590);
            g.DrawString("Վանաձոր - 2 0 2 3", new Font("", 20, FontStyle.Bold), new SolidBrush(Color.White), 500, 680);
            g.DrawLine(new Pen(Color.LightBlue, 5), 440, 735, 830, 735);
            g.DrawLine(new Pen(Color.LightBlue, 5), 400, 755, 870, 755);
            timer1.Enabled = false;
        }
        private void Form1_MouseDown(object sender, MouseEventArgs e)
        {
                    Environment.Exit(0);
        }
        private void pictureBox2_Click(object sender, EventArgs e)
        {
            Form2 f = new Form2();
            f.Show();
        }
    }
}

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
namespace Diplomayin_Irina
{
    public partial class Form2 : Form
    {
        public static string s,s1;
        public Form2()
        {
            InitializeComponent();
            this.BackColor = Color.DarkGreen;
        }
        private void Form2_Load(object sender, EventArgs e)
        {
            pictureBox1.Top = 650;
            pictureBox1.Left = 660;
            pictureBox1.Width = 130;
            pictureBox1.Height = 90;
           label1.Font = new Font("", 55, FontStyle.Bold);
           label1.ForeColor = Color.Yellow;
           label1.Left = 340;
           label1.Top = 20;
           label1.Text = "ՍԻՄՊԼԵՔՍ ՄԵԹՈԴ";
           label2.Font = new Font("", 35, FontStyle.Bold|FontStyle.Italic);
           label2.ForeColor = Color.WhiteSmoke;
           label2.Left = 275;
           label2.Top = 140;
           label2.Text = "Գծային ծրագրավորման խնդիրների \n        լուծման ունիվերսալ մեթոդ";
           label3.Font = new Font("", 30, FontStyle.Bold|FontStyle.Italic);
           label3.ForeColor = Color.Yellow;
           label3.Left = 595;
           label3.Top = 400;
           label3.Text = "Ներմուծել";
           label4.Left = -200;
           comboBox1.Width = 400;
           comboBox1.Height = 40;
           comboBox1.BackColor = Color.White;
           comboBox1.ForeColor = Color.DarkGreen;
           comboBox1.Font = new Font("arial latarm", 20, FontStyle.Bold);
           comboBox1.Left = 285;
           comboBox1.Top = 500;
           comboBox1.Text = "       Անհայտների քանակ";
           for (int i = 2; i <= 5; i++)
               comboBox1.Items.Add(i);
           comboBox2.Width = 410;
           comboBox2.Height = 40;
           comboBox2.BackColor = Color.White;
           comboBox2.ForeColor = Color.DarkGreen;
           comboBox2.Font = new Font("arial latarm", 20, FontStyle.Bold);
           comboBox2.Left = 750;
           comboBox2.Top = 500;
           comboBox2.Text = " Սահմանափակումների քանակ";
           for (int i = 2; i <= 5; i++)
               comboBox2.Items.Add(i);
        }
        private void Form2_MouseDown(object sender, MouseEventArgs e)
        {
            Form1 f = new Form1();
            f.Show();
        }
        private void label1_Click(object sender, EventArgs e)
        {
        }
        private void label4_Click(object sender, EventArgs e)
        {
        }
        private void pictureBox1_Click(object sender, EventArgs e)
        {
            s = comboBox1.Text;
            s1 = comboBox2.Text;
            if ((string.Compare(s, "2") == 0 || string.Compare(s, "3") == 0 || string.Compare(s, "4") == 0 || string.Compare(s, "5") == 0) && (string.Compare(s1, "2") == 0 || string.Compare(s1, "3") == 0 || string.Compare(s1, "4") == 0 || string.Compare(s1, "5") == 0))
            {
                Form3.s = s;
                Form3.s1 = s1;
                Form3 f = new Form3();
                f.Show();
            }
            else
            {
                MessageBox.Show("Տվյալները ընտրված չեն", "ՀԱՂՈՐԴԱԳՐՈւԹՅՈւՆ", MessageBoxButtons.OK, MessageBoxIcon.Stop);
            }
        }
    }
}
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
namespace Diplomayin_Irina
{
    public partial class Form3 : Form
    {
        public static string s = Form2.s;
        public static string s1 = Form2.s1;

        public static int i, j, i1, j1, x, y, xx, x1, y1, k, n, m, n1, m1, h, p,ss;
        public static bool b = false, b1 = false;
        TextBox[] nf;
       public static double[,] mas;
        TextBox[] z;
        TextBox[] zt;
        TextBox[] zs;
        ComboBox[] B;
        public Form3()
        {
            InitializeComponent();
            this.BackColor = Color.DarkGreen;
        }
        private void Form3_Load(object sender, EventArgs e)
        {
            pictureBox1.Top = 680;
            pictureBox1.Left = 1100;
            pictureBox1.Width = 130;
            pictureBox1.Height = 90;
            label1.Font = new Font("", 25, FontStyle.Bold|FontStyle.Italic);
            label1.ForeColor = Color.Yellow;
            label1.Left =-600;
            label1.Top = 700;
            label1.Text = "Շարունակել";
            label1.Cursor = Cursors.Hand;
            Graphics g = this.CreateGraphics();
            m = Convert.ToInt32(s);
            m++;
            n = Convert.ToInt32(s1);
            z = new TextBox[n * m];
            zt = new TextBox[n];
            zs = new TextBox[m];
            B = new ComboBox[n];
            nf = new TextBox[m];
            if (m - 1 == 2) xx = 470; else if (m - 1 == 3) xx = 400; else if (m - 1 == 4) xx = 310; else xx = 250;
            x = xx;
            y = 120; k = 0;
            comboBox1.Font = new Font("", 15, FontStyle.Bold);
            comboBox1.Width = 60;
            comboBox1.Height = 6;
            comboBox1.Top = y;
            comboBox1.Left = -500;
            comboBox1.Items.Add("min");
            comboBox1.Items.Add("max");
            comboBox1.Text = "min";
            timer1.Enabled = true;
            h = 1;
            j = 0;
        }
        private void Form3_MouseDown(object sender, MouseEventArgs e)
        {
            Form2 f = new Form2();
            f.Show();
        }
        private void timer1_Tick(object sender, EventArgs e)
        {
            Graphics g = this.CreateGraphics();
            g.DrawString("ՍԱՀՄԱՆԱՓԱԿՈՒՄՆԵՐ", new Font("", 35, FontStyle.Bold | FontStyle.Italic), new SolidBrush(Color.LightYellow), 402, 18);
            g.DrawString("ՍԱՀՄԱՆԱՓԱԿՈՒՄՆԵՐ", new Font("", 35, FontStyle.Bold | FontStyle.Italic), new SolidBrush(Color.Yellow), 400, 20);
            for (i = 0; i < z.Length; i++)
            {
                z[i] = new TextBox();
                z[i].Font = new Font("", 28, FontStyle.Bold);
                z[i].Width = 65;
                z[i].Height = 60;
                z[i].Top = y;
                z[i].Left = x;
                this.Controls.Add(z[i]);
                if (h < m - 1) g.DrawString("+", new Font("", 25, FontStyle.Bold), new SolidBrush(Color.White), x + 120, y + 10);
                if (h != m) g.DrawString("X" + Convert.ToString(h), new Font("", 24, FontStyle.Bold), new SolidBrush(Color.White), x + 70, y + 10);
                if (h == m - 1)
                {
                    x = x + 130;
                    B[j] = new ComboBox();
                    B[j].Font = new Font("", 25, FontStyle.Bold);
                    B[j].Width = 65;
                    B[j].Height = 60;
                    B[j].Top = y;
                    B[j].Left = x;
                    B[j].Items.Add(" =");
                    B[j].Items.Add("<=");
                    B[j].Items.Add(">=");
                    B[j].Text = "<=";
                    this.Controls.Add(B[j]);
                    j++;               
                    x = x - 70;
                }
                x = x + 160;
                k++; h++;
                if (k == m) { y += 65; x = xx; h = 1; k = 0; }
            }
            if (m - 1 == 2) x1 = 600; else if (m - 1 == 3) x1 = 580; if (m - 1 == 4) x1 = 490; else if (m - 1 == 5) x1 = 470;
            for (i = 1; i < m; i++)
            {
                g.DrawString("X" + Convert.ToString(i) + ">=0", new Font("", 20, FontStyle.Bold), new SolidBrush(Color.White), x1, y + 10);
                if (i < m - 1) g.DrawString(", ", new Font("", 20, FontStyle.Bold), new SolidBrush(Color.White), x1 + 88, y + 10);
                x1 = x1 + 100;
            }
            g.DrawString("ՆՊԱՏԱԿԱՅԻՆ ՖՈՒՆԿՑԻԱ", new Font("", 35, FontStyle.Bold | FontStyle.Italic), new SolidBrush(Color.LightYellow), 382, y + 65);
            g.DrawString("ՆՊԱՏԱԿԱՅԻՆ ՖՈՒՆԿՑԻԱ", new Font("", 35, FontStyle.Bold | FontStyle.Italic), new SolidBrush(Color.Yellow), 384, y + 67);
            h = 1;
            g.DrawString("F     =", new Font("", 40, FontStyle.Bold | FontStyle.Italic), new SolidBrush(Color.Yellow), x - 30, y + 153);
            comboBox1.Top = y + 180;
            comboBox1.Left = x + 25;
            x = x + 148;
            for (i = 0; i < m - 1; i++)
            {
                nf[i] = new TextBox();
                nf[i].Font = new Font("", 28, FontStyle.Bold);
                nf[i].Width = 65;
                nf[i].Height = 60;
                nf[i].Top = y + 157;
                nf[i].Left = x;
                this.Controls.Add(nf[i]);
                if (h < m - 1) g.DrawString("+", new Font("", 25, FontStyle.Bold), new SolidBrush(Color.White), x + 120, y + 163);
                if (h != m) g.DrawString("X" + Convert.ToString(h), new Font("", 24, FontStyle.Bold), new SolidBrush(Color.White), x + 70, y + 163);
                x = x + 160;
                h++;
            }
              timer1.Enabled = false;
        }
        private void timer2_Tick(object sender, EventArgs e)
        {       
        }
        private void label1_Click(object sender, EventArgs e)
        { 
        }
        private void pictureBox1_Click(object sender, EventArgs e)
        {
            m1 = m;
            n1 = n + 1;
            for (i = 0; i < n; i++)
                if (string.Compare(B[i].Text, "<=") == 0 || string.Compare(B[i].Text, ">=") == 0) m1++;
            mas = new double[n1, m1];
            i = 0; j = 0; k = 0; p = m - 1;
            while (k < n * m)
            {
                mas[i, j] = Convert.ToDouble(z[k].Text);
                j++; k++;
                if (k == p)
                {
                    mas[i, m1 - 1] = Convert.ToDouble(z[k].Text); i++; j = 0; k++; p = p + m;
                }
            }
            for (j = 0; j < m - 1; j++) mas[n1 - 1, j] =(-1)*Convert.ToDouble(nf[j].Text);   
            if (m1 != m)
            {
                p = m - 1; j1 = 0;
                for (i = 0; i < n1 - 1; i++)
                    if (string.Compare(B[i].Text, "<=") == 0)
                    {
                        mas[i, p + j1] = 1;
                        for (j = p; j < m1 - 1; j++)
                            if (j != p + j1) mas[i, j] = 0;
                        j1++;
                    }
                    else
                        if (string.Compare(B[i].Text, ">=") == 0)
                        {
                            mas[i, p + j1] = -1;
                            for (j = p; j < m1 - 1; j++)
                                if (j != p + j1) mas[i, j] = 0;
                            j1++;
                        }
                        else
                            for (j = p; j < m1 - 1; j++) mas[i, j] = 0;
            }
            if (string.Compare(comboBox1.Text, "max") == 0) ss = 1; else ss = 0;
            Form4.mas = mas;
            Form4.n1 = n1;
            Form4.m1 = m1;
            Form4.m = m;
            Form4.ss = ss;
            Form4 f1 = new Form4();
            f1.Show();
        }
    }
}

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
namespace Diplomayin_Irina
{
    public partial class Form4 : Form
    {
        public static double[,] mas = Form3.mas;
        public static int n1 = Form3.n1;
        public static int m1 = Form3.m1;
        public static int m = Form3.m;
        public static int i=0, j=0, p,x,y,q=0,i1, j1, i2,x1,y1,min;
        public static int ss = Form3.ss;
        public static int[] tox;
        public static int[] syun;
        public Form4()
        {
            InitializeComponent();
            this.BackColor = Color.DarkGreen;
        }
        private void Form4_Load(object sender, EventArgs e)
        {
            label1.Font = new Font("", 25, FontStyle.Bold | FontStyle.Italic);
            label1.ForeColor = Color.Yellow;
            label1.Left = -600;
            label1.Top = 700;
            label1.Text = "Շարունակել";
            label1.Cursor = Cursors.Hand;   
            tox = new int[n1];
            syun = new int[m1];
            timer1.Enabled = true;
        }
        private void Form4_MouseDown(object sender, MouseEventArgs e)
        {
            Form3 f = new Form3();
            f.Show();
        }
        private void timer1_Tick(object sender, EventArgs e)
        {
            Graphics g = this.CreateGraphics();
            g.DrawString("ՍԻՄՊԼԵՔՍ ԱՂՅՈՒՍԱԿ", new Font("", 35, FontStyle.Bold | FontStyle.Italic), new SolidBrush(Color.LightYellow), 402, 18);
            g.DrawString("ՍԻՄՊԼԵՔՍ ԱՂՅՈՒՍԱԿ", new Font("", 35, FontStyle.Bold | FontStyle.Italic), new SolidBrush(Color.Yellow), 400, 20);
           for (i = 0; i < n1; i++) tox[i] = 0;
            for (j = 0; j < m1 - 1; j++)
            {
                i1 = 0;
                for (i = 0; i < n1 - 1; i++)
                    if (mas[i,j] == 0) i1++; else { j1 = i; i2 = j; }
                if (i1 == n1 - 2) tox[j1] = j + 1;
                if (mas[j1,i2] != 1) tox[j1] = 0;
            }
            if (m - 1 == 2) x1 = 600; else if (m - 1 == 3) x1 = 580; if (m - 1 == 4) x1 = 490;
            else if (m - 1 == 5) x1 = 470; else if (m - 1 == 6) x1 = 400; else if (m - 1 == 7) x1 = 350; else x1 = 500;
            y1=120;
            for (i1 = 1; i1 < m1; i1++)
            {
                g.DrawString("X" + Convert.ToString(i1), new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Yellow), x1, y1);
                x1 += 90;
            }
            g.DrawString("B", new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Yellow), x1, y1);
            if (m - 1 == 2) x1 = 600; else if (m - 1 == 3) x1 = 580; if (m - 1 == 4) x1 = 490;
            else if (m - 1 == 5) x1 = 470; else if (m - 1 == 6) x1 = 400; else if (m - 1 == 7) x1 = 350; else x1 = 500;
            x = x1 - 90;
            y=y1+60;
            for (i = 0; i < n1; i++)
            {
                if (i < n1 - 1)
                    if (tox[i] != 0)
                    { g.DrawString("X" + Convert.ToString(tox[i]), new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Yellow), x, y); x = x + 90; }
                    else x = x + 90;
                if (i == n1 - 1) { g.DrawString("F", new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Red), x, y); x = x + 90; }         
               for (j = 0; j < m1; j++)
                {
                    g.DrawString(Convert.ToString(mas[i,j]), new Font("", 25, FontStyle.Bold), new SolidBrush(Color.White), x, y);
                   x = x + 90; 
                }
               x = x1 - 90;
               y = y + 60;
            }
            label1.Left = 600;
            timer1.Enabled = false;
        }
        private void label1_Click(object sender, EventArgs e)
        {  
            Graphics g = this.CreateGraphics();
            SolidBrush v1 = new SolidBrush(Color.DarkGreen);
            g.FillRectangle(v1, 0, 110, 1400, 700);   
           /* for (i = 0; i < n1; i++) tox[i] = 0;
            for (j = 0; j < m1 - 1; j++)
            {
                i1 = 0;
                for (i = 0; i < n1 - 1; i++)
                    if (mas[i,j] == 0) i1++; else { j1 = i; i2 = j; }
                if (i1 == n1 - 2) tox[j1] = j + 1;
                if (mas[j1,i2] != 1) tox[j1] = 0;
            }
            if (m - 1 == 2) x1 = 600; else if (m - 1 == 3) x1 = 580; if (m - 1 == 4) x1 = 490;
            else if (m - 1 == 5) x1 = 470; else if (m - 1 == 6) x1 = 400; else if (m - 1 == 7) x1 = 350; else x1 = 500;
            y1=120;
            for (i1 = 1; i1 < m1; i1++)
            {
                g.DrawString("X" + Convert.ToString(i1), new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Yellow), x1, y1);
                x1 += 90;
            }
            g.DrawString("B", new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Yellow), x1, y1);
            if (m - 1 == 2) x1 = 600; else if (m - 1 == 3) x1 = 580; if (m - 1 == 4) x1 = 490;
            else if (m - 1 == 5) x1 = 470; else if (m - 1 == 6) x1 = 400; else if (m - 1 == 7) x1 = 350; else x1 = 500;
            x = x1 - 90;
            y=y1+60;
            for (i = 0; i < n1; i++)
            {
                if (i < n1 - 1)
                    if (tox[i] != 0)
                    { g.DrawString("X" + Convert.ToString(tox[i]), new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Yellow), x, y); x = x + 90; }
                    else x = x + 90;
                if (i == n1 - 1) { g.DrawString("F", new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Red), x, y); x = x + 90; }

                for (j = 0; j < m1; j++)
                {
                    g.DrawString(Convert.ToString(mas[i, j]), new Font("", 25, FontStyle.Bold), new SolidBrush(Color.White), x, y);
                    x = x + 90;
                }
                x = x1 - 90;
                y = y + 60;
            }
            //ստուգել լուծման օպտիմալությունը 
            for (i = 0; i < n1; i++) tox[i] = 0;
            for (j = 0; j < m1 - 1; j++)
            {
                i1 = 0;
                for (i = 0; i < n1 - 1; i++)
                    if (mas[i,j] == 0) i1++; else { j1 = i; i2 = j; }
                if (i1 == n1 - 2) tox[j1] = j + 1;
                if (mas[j1,i2] != 1) tox[j1] = 0;
            }
            int min;
          /*  for (i = 0; i < n; i++)
            {
                if (i < n - 1) if (tox[i] != 0) cout << "x" << tox[i] << "\t"; else cout << "\t";
                if (i == n - 1) cout << "F\t";
                for (j = 0; j < k; j++)
                {
                    cout << setprecision(3) << mas[i][j] << "\t";
                }
                cout << " " << endl;
            }*/
            int kpol = 0;
            for (j = 0; j < m1-1; j++) // նայել m1-1
            {
                if (ss == 1)
                {
                    if (mas[n1 - 1,j] >= 0)
                        kpol++;
                }
                else
                {
                    if (mas[n1 - 1,j] <= 0)
                        kpol++;
                }
            }
            if (kpol == m1 - 1) // նայել m1-1
            {
                if (ss == 1)
                    g.DrawString("Fmax=" + Convert.ToString(mas[n1 - 1, m1 - 1]), new Font("", 30, FontStyle.Bold), new SolidBrush(Color.Red),600,650);
                else
                    g.DrawString("Fmin=" + Convert.ToString(mas[n1 - 1, m1 - 1]), new Font("", 30, FontStyle.Bold), new SolidBrush(Color.Red),600,650);
                label1.Left = -600; goto w;
            }                
         min = 0;
            if (ss == 1)
            {
                for (j = 1; j < m1-1; j++)
                    if (mas[n1 - 1,j] < mas[n1 - 1,min]) min = j;
            }
            else
            {
                for (j = 1; j < m1-1; j++)
                    if (mas[n1 - 1,j] > mas[n1 - 1,min]) min = j;
            }
           // g.DrawString("սյուն: " + Convert.ToString(min), new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Yellow), 20, 500);
            double t;
            t = mas[n1 - 1,min];
            int myn = 0;
            double r = 0, z = 0;
            for (i = 0; i < n1-1; i++) //
                if (mas[i,min] <= 0) z++;
            if (z == n1 - 1) { g.DrawString("Խնդիրը լուծում չունի", new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Yellow), 600, 650); label1.Left = -600; goto w; }
            for (i = 0; i < n1-1; i++) //
            {
                if (mas[i,min] <= 0) continue; else { z = (mas[i,m1 - 1]) / (mas[i,min]); myn = i; }
                for (i = i + 1; i < n1-1; i++)
                    if (mas[i,min] > 0)
                    { r = mas[i,m1 - 1] / mas[i,min]; if (z > r) myn = i; }
            }
           // g.DrawString("տող: " + Convert.ToString(myn), new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Yellow), 150,500);
           // g.DrawString("էլեմենտ: " + Convert.ToString(mas[myn,min]), new Font("", 20, FontStyle.Bold), new SolidBrush(Color.Yellow), 100, 680);
            //g.DrawString(Convert.ToString(mas[myn, min]), new Font("", 20, FontStyle.Bold), new SolidBrush(Color.Red), x1+myn*90, y1+min*60);
            double l = 0;
            l = mas[myn,min];
            for (j = 0; j < m1; j++)
            {
                mas[myn,j] = mas[myn,j] / l;
            }
            double p = 0;
            for (i = 0; i < n1; i++)
            {
                p = mas[i,min];
                if (i != myn)
                {
                    for (j = 0; j < m1; j++)
                    {
                        mas[i,j] = mas[i,j] - mas[myn,j] * p;
                    }
                }
           }
            //Տպել աղյուսակը
         w: for (i = 0; i < n1; i++) tox[i] = 0;
            for (j = 0; j < m1 - 1; j++)
            {
                i1 = 0;
                for (i = 0; i < n1 - 1; i++)
                    if (mas[i, j] == 0) i1++; else { j1 = i; i2 = j; }
                if (i1 == n1 - 2) tox[j1] = j + 1;  
                if (mas[j1, i2] != 1) tox[j1] = 0;
            }
            if (m - 1 == 2) x1 = 600; else if (m - 1 == 3) x1 = 580; if (m - 1 == 4) x1 = 490;
            else if (m - 1 == 5) x1 = 470; else if (m - 1 == 6) x1 = 400; else if (m - 1 == 7) x1 = 350; else x1 = 500;
            y1 = 120;
            for (i1 = 1; i1 < m1; i1++)
            {
                g.DrawString("X" + Convert.ToString(i1), new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Yellow), x1, y1);
                x1 += 90;
            }
            g.DrawString("B", new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Yellow), x1, y1);
            if (m - 1 == 2) x1 = 600; else if (m - 1 == 3) x1 = 580; if (m - 1 == 4) x1 = 490;
            else if (m - 1 == 5) x1 = 470; else if (m - 1 == 6) x1 = 400; else if (m - 1 == 7) x1 = 350; else x1 = 500;
            x = x1 - 90;
            y = y1 + 60;
            for (i = 0; i < n1; i++)
            {
                if (i < n1 - 1)
                    if (tox[i] != 0)
                    { g.DrawString("X" + Convert.ToString(tox[i]), new Font("", 25, FontStyle.Bold), new SolidBrush(Color.Yellow), x, y); x = x + 90; }
                    else x = x + 90;
                if (i == n1 - 1) { g.DrawString("F", new Font("", 26, FontStyle.Bold), new SolidBrush(Color.Red), x, y); x = x + 90; }
                for (j = 0; j < m1; j++)
                {
                    double aa = mas[i, j] - (int)mas[i, j];
                    if(aa==0)
                    g.DrawString(Convert.ToString(mas[i, j]), new Font("", 25, FontStyle.Bold), new SolidBrush(Color.White), x, y);
                    else
                        g.DrawString(String.Format("{0:F1}", mas[i, j]), new Font("", 25, FontStyle.Bold), new SolidBrush(Color.White), x, y);
                    x = x + 90;
                }
                x = x1 - 90;
                y = y + 60;
            }
            //for (i1 = 0; i1 < m1 - 1; i1++) cout << "X" << i1 + 1 << "\t";
            //cout << "b\n\n";
           /* for (i = 0; i < n1; i++)
            {
                if (i < n - 1) if (tox[i] != 0) cout << "x" << tox[i] << "\t"; else cout << "\t";
                if (i == n - 1) cout << "F\t";
                for (j = 0; j < k; j++)
                {
                    cout << setprecision(3) << mas[i][j] << "\t";
                }
                cout << " " << endl;
            }*/
           /* kpol = 0;
            for (j = 0; j < m1-1; j++)
            {
                if (ss == 1)
                {
                    if (mas[n1 - 1,j] >= 0)
                        kpol++;
                }
                else
                {
                    if (mas[n1 - 1,j] <= 0)
                        kpol++;
                }
            }
            if (kpol!= m1-1) goto w;*/
        }
    }
}


















