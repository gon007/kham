using System;
using System.Windows.Forms;
using Game_over.Models;

namespace Game_over
{
    public partial class Form1 : Form
    {
        Advisor advisor1;
        Advisor advisor2;

        public Form1()
        {
            InitializeComponent();

            advisor1 = new Advisor { FirstName = "อ.สมชาย", LastName = "ใจดี" };
            advisor1.Students.Add(new Student { FirstName = "แยทแมน", LastName = "ประยุด", StudentID = "67345002-8", Major = "CS", Grade = 4.0 });
            advisor1.Students.Add(new Student { FirstName = "วิชั่น", LastName = "ชัชชาติ", StudentID = "673450194-8", Major = "IT", Grade = 3.5 });

            advisor2 = new Advisor { FirstName = "อ.จี้ไล", LastName = "รักเรียน" };
            advisor2.Students.Add(new Student { FirstName = "มายเมทเนต", LastName = "สุกดี", StudentID = "673450192-5", Major = "IT", Grade = 2.5 });
            advisor2.Students.Add(new Student { FirstName = "ธนาเทียม", LastName = "มาสาย", StudentID = "673450193-7", Major = "IT", Grade = 3.2 });
        }

        private void button3_Click(object sender, EventArgs e)
        {
            // รวมรายชื่อนักศึกษาจากอาจารย์ทั้งสอง
            var allStudents = advisor1.Students.Concat(advisor2.Students)
                                .OrderByDescending(s => s.Grade)
                                .ToList();

            var topStudent = allStudents[0]; // นักศึกษาที่ได้เกรดสูงสุด
            var secondStudent = allStudents[1]; // นักศึกษาที่ได้เกรดรองลงมา

            // แสดงผลนักศึกษาเกรดสูงสุด
            maskedTextBox5.Text = topStudent.FirstName + " " + topStudent.LastName;
            maskedTextBox11.Text = topStudent.StudentID;
            maskedTextBox6.Text = topStudent.Grade.ToString("F");
            maskedTextBox19.Text = topStudent.Major;
            maskedTextBox21.Text = "ดีใจด้วย";

            // แสดงผลนักศึกษาที่ได้เกรดรองลงมา
            maskedTextBox13.Text = secondStudent.FirstName + " " + secondStudent.LastName;
            maskedTextBox14.Text = secondStudent.StudentID;
            maskedTextBox12.Text = secondStudent.Grade.ToString("F");
            maskedTextBox20.Text = secondStudent.Major;
        }


        private void button1_Click(object sender, EventArgs e)
        {
            maskedTextBox4.Text = advisor1.Students[1].FirstName + " " + advisor1.Students[1].LastName;
            maskedTextBox1.Text = advisor1.Students[0].FirstName + " " + advisor1.Students[0].LastName;
            maskedTextBox8.Text = advisor1.Students[1].StudentID;
            maskedTextBox7.Text = advisor1.Students[0].StudentID;
            maskedTextBox15.Text = advisor1.Students[1].Major;
            maskedTextBox18.Text = advisor1.Students[0].Major;
        }

        private void button2_Click(object sender, EventArgs e)
        {
            maskedTextBox2.Text = advisor2.Students[0].FirstName + " " + advisor2.Students[0].LastName;
            maskedTextBox9.Text = advisor2.Students[0].StudentID;
            maskedTextBox3.Text = advisor2.Students[1].FirstName + " " + advisor2.Students[1].LastName;
            maskedTextBox10.Text = advisor2.Students[1].StudentID;
            maskedTextBox17.Text = advisor2.Students[0].Major;
            maskedTextBox16.Text = advisor2.Students[1].Major;
        }

        private void button4_Click(object sender, EventArgs e)
        {
            foreach (Control ctrl in Controls)
            {
                if (ctrl is MaskedTextBox)
                    ((MaskedTextBox)ctrl).Clear();

                if (ctrl is GroupBox)
                {
                    foreach (Control subCtrl in ctrl.Controls)
                    {
                        if (subCtrl is MaskedTextBox)
                            ((MaskedTextBox)subCtrl).Clear();
                    }
                }
            }
        }

        private void button5_Click(object sender, EventArgs e)
        {
            {
                // รวมรายชื่อนักศึกษาทั้งหมดจากที่ปรึกษาทั้งสอง
                var allStudents = advisor1.Students.Concat(advisor2.Students)
                                    .OrderByDescending(s => s.Grade)
                                    .ToList();

                // แสดงข้อมูลบนหน้าจอ
                string message = "รายชื่อนักศึกษาทั้งหมด:\n";
                foreach (var student in allStudents)
                {
                    message += $"{student.FirstName} {student.LastName}, รหัส: {student.StudentID}, สาขา: {student.Major}, เกรด: {student.Grade:F2}\n";
                }

                // แสดงใน MessageBox
                MessageBox.Show(message, "ข้อมูลนักศึกษา", MessageBoxButtons.OK, MessageBoxIcon.Information);
            }
        }
    }
}
