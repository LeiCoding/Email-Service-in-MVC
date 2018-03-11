using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.Mvc;
using EmailService.Models;
using System.Net;
using System.Net.Mail;

namespace EmailService.Controllers
{
    public class EmailSetupController : Controller
    {
        // GET: GmailSetup
        public ActionResult Index()
        {
            return View();
        }

        [HttpPost]
        public ActionResult Index(EmailService.Models.Email model)
        {
            MailMessage mm = new MailMessage("gmailaddress",model.To);
            mm.Subject = model.Subject;
            mm.Body = model.Body;
            mm.IsBodyHtml = false;

            SmtpClient smtp = new SmtpClient();
            smtp.Host = "smtp.gmail.com";
            smtp.Port = 587;
            smtp.EnableSsl = true;

            NetworkCredential nc = new NetworkCredential("gmailaddress", "password");
            smtp.UseDefaultCredentials = false;
            smtp.Credentials = nc;
            smtp.Send(mm);
            ViewBag.Message = "Mail has been sent";

            return View();
        }

    }
}
