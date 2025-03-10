# Inheritance
using static System.Windows.Forms.DataFormats;

namespace WinFormsApp3
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void btnPikachu_Click(object sender, EventArgs e)
        {
            // โหลดภาพ Pikachu ลงใน PictureBox
            string imagePath = "C:\\Users\\Advice_BP\\Downloads\\WinFormsApp3_Final\\WinFormsApp3\\WinFormsApp3\\025.png"; // ต้องมีไฟล์รูปภาพนี้อยู่ในโฟลเดอร์โปรเจกต์
            try
            {
                pictureBox1.Image = Image.FromFile(imagePath);
            }
            catch (Exception ex)
            {
                MessageBox.Show("ไม่พบไฟล์รูปภาพ: " + ex.Message);
            }
            maskedTextBox1.Text = "Pikachu";
            maskedTextBox2.Text = "Electric";
            maskedTextBox3.Text = "Active";
            
        }

        private void pictureBox1_Click(object sender, EventArgs e)
        {

        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }

        private void btnCharizard_Click(object sender, EventArgs e)
        {
            // โหลดภาพ Pikachu ลงใน PictureBox
            string imagePath = "C:\\Users\\Advice_BP\\Downloads\\WinFormsApp3_Final\\WinFormsApp3\\WinFormsApp3\\Pokémon_Charizard_art.png"; // ต้องมีไฟล์รูปภาพนี้อยู่ในโฟลเดอร์โปรเจกต์
            try
            {
                pictureBox1.Image = Image.FromFile(imagePath);
            }
            catch (Exception ex)
            {
                MessageBox.Show("ไม่พบไฟล์รูปภาพ: " + ex.Message);
            }
            maskedTextBox1.Text = "Charizard";
            maskedTextBox2.Text = "\"Fire/Flying\";";
            maskedTextBox3.Text = "Active";
        }

        private void btnBulbasaur_Click(object sender, EventArgs e)
        {
            // โหลดภาพ Pikachu ลงใน PictureBox
            string imagePath = "C:\\Users\\Advice_BP\\Downloads\\WinFormsApp3_Final\\WinFormsApp3\\WinFormsApp3\\Pokémon_Bulbasaur_art.png"; // ต้องมีไฟล์รูปภาพนี้อยู่ในโฟลเดอร์โปรเจกต์
            try
            {
                pictureBox1.Image = Image.FromFile(imagePath);
            }
            catch (Exception ex)
            {
                MessageBox.Show("ไม่พบไฟล์รูปภาพ: " + ex.Message);
            }
            maskedTextBox1.Text = "Bulbasaur";
            maskedTextBox2.Text = "\"Grass/Poison\"; ";
            maskedTextBox3.Text = "Active";
        }

        private void btnSquirtle_Click(object sender, EventArgs e)
        {
            // โหลดภาพ Pikachu ลงใน PictureBox
            string imagePath = "C:\\Users\\Advice_BP\\Downloads\\WinFormsApp3_Final\\WinFormsApp3\\WinFormsApp3\\007.png"; // ต้องมีไฟล์รูปภาพนี้อยู่ในโฟลเดอร์โปรเจกต์
            try
            {
                pictureBox1.Image = Image.FromFile(imagePath);
            }
            catch (Exception ex)
            {
                MessageBox.Show("ไม่พบไฟล์รูปภาพ: " + ex.Message);
            }
            maskedTextBox1.Text = "Squirtle";
            maskedTextBox2.Text = "\"Water\" ";
            maskedTextBox3.Text = "Active";
        }

        private void btnJigglypuff_Click(object sender, EventArgs e)
        {
            // โหลดภาพ Pikachu ลงใน PictureBox
            string imagePath = "C:\\Users\\Advice_BP\\Downloads\\WinFormsApp3_Final\\WinFormsApp3\\WinFormsApp3\\jigglypuff.png"; // ต้องมีไฟล์รูปภาพนี้อยู่ในโฟลเดอร์โปรเจกต์
            try
            {
                pictureBox1.Image = Image.FromFile(imagePath);
            }
            catch (Exception ex)
            {
                MessageBox.Show("ไม่พบไฟล์รูปภาพ: " + ex.Message);
            }
            maskedTextBox1.Text = "Jigglypuff";
            maskedTextBox2.Text = "\\Normal / Fairy\" ";
            maskedTextBox3.Text = "Active";
        }

        private void btnMeowth_Click(object sender, EventArgs e)
        {
            // โหลดภาพ Pikachu ลงใน PictureBox
            string imagePath = "C:\\Users\\Advice_BP\\Downloads\\WinFormsApp3_Final\\WinFormsApp3\\WinFormsApp3\\meowth.png"; // ต้องมีไฟล์รูปภาพนี้อยู่ในโฟลเดอร์โปรเจกต์
            try
            {
                pictureBox1.Image = Image.FromFile(imagePath);
            }
            catch (Exception ex)
            {
                MessageBox.Show("ไม่พบไฟล์รูปภาพ: " + ex.Message);
            }
            maskedTextBox1.Text = "Meowth";
            maskedTextBox2.Text = "Normal";
            maskedTextBox3.Text = "Active";
        }

        private void label1_Click(object sender, EventArgs e)
        {
            pictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;
            pictureBox1.Image = null;
            lblPokemonName.Text = "Name: ";
            lblPokemonType.Text = "Type: ";
            lblPokemonStatus.Text = "Status: ";
        }


        private void label2_Click(object sender, EventArgs e)
        {

        }

        private void label3_Click(object sender, EventArgs e)
        {

        }

        private void label4_Click(object sender, EventArgs e)
        {

        }

    }
}
