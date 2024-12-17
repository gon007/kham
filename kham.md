namespace WinFormsApp3
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void label2_Click(object sender, EventArgs e)
        {

        }

        private void label3_Click(object sender, EventArgs e)
        {

        }

        private void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)
        {

        }

        private void button2_Click(object sender, EventArgs e)
        {
            string inputNum1 = Num1.Text;
            string inputNum2 = Num2.Text;

            int iNum1 = int.Parse(inputNum1);
            int iNum2 = int.Parse(inputNum1);
            int iresult = iNum1 - iNum2;

            result.Text = iresult.ToString();
        }

        private void button3_Click(object sender, EventArgs e)
        {
            Num1.Text = "";
            Num2.Text = "";
            result.Text = "";

        }

        private void button1_Click(object sender, EventArgs e)
        {
            string inputNum1 = Num1.Text;
            string inputNum2 = Num2.Text;

            int iNum1 = int.Parse(inputNum1);
            int iNum2 = int.Parse(inputNum1);
            int iresult = iNum1 + iNum2;

            result.Text = iresult.ToString();


        }

        private void button4_Click(object sender, EventArgs e)
        {
            string inputNum1 = Num1.Text;
            string inputNum2 = Num2.Text;

            int iNum1 = int.Parse(inputNum1);
            int iNum2 = int.Parse(inputNum1);
            int iresult = iNum1 * iNum2;

            result.Text = iresult.ToString();
        }

        private void button5_Click(object sender, EventArgs e)
        {
            string inputNum1 = Num1.Text;
            string inputNum2 = Num2.Text;

            int iNum1 = int.Parse(inputNum1);
            int iNum2 = int.Parse(inputNum1);
            int iresult = iNum1 / iNum2;

            result.Text = iresult.ToString();
        }
    }
}
