```csharp
Form1:
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace baitap
{
    public partial class Form1 : Form1
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void form2ToolStripMenuItem_Click(object sender, EventArgs e)
        {
            {
                OpenFileDialog oFile = new OpenFileDialog();
                oFile.Filter = "Bitmap file|*.bmp|JPEG file|*.jpg|PNG file|*.png";
                if (oFile.ShowDialog() == DialogResult.OK)
                {
                    Form2 form2 = new Form2();
                    form2.MdiParent = this;
                    form2.Show();
                }
            }
        }

        private void openToolStripMenuItem_Click(object sender, EventArgs e)
        {

        }
    }
}
Form2:
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace baitap
{
    public partial class Form2 : Form
    {
        public Form2(string imageFile)
        {
            InitializeComponent();
            pictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;
            pictureBox1.Image = Image.FromFile(imageFile);
            Text = imageFile.Substring(imageFile.LastIndexOf('\\') + 1);
        }

        public Form2()
        {
            InitializeComponent();
        }

        private void pictureBox1_Click(object sender, EventArgs e)
        {

        }
    }
}
