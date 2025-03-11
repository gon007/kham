using System.Collections.Generic;

namespace Game_over.Models
{
    public class Advisor
    {
        public string FirstName { get; set; }
        public string LastName { get; set; }
        public List<Student> Students { get; set; } = new List<Student>();

        public Student GetTopStudent() => Students.OrderByDescending(s => s.Grade).FirstOrDefault();
        public Student GetSecondStudent() => Students.OrderByDescending(s => s.Grade).Skip(1).FirstOrDefault();
    }
}
