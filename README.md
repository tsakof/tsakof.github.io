
<i> tsakof.github.io </i> Version 1.0 20/10/2015 </b>
---------------------------------------------------------------------------

Γενική περιγραφή Ιστοσελίδας
-----------------------------------

Η ιστοσελίδα αυτή κατασκευάστηκε στα πλαίσια της πρώτης εργασίας της θεματικής ενότητας:
"Πληροφορίες σε Κοινωνικά Συστήματα" του μεταπτυχιακού προγράμματος "Κοινωνικά Πληροφοριακά Συστήματα" του ανοικτού πανεπιστημίου Κύπρου.
Σκοπός της εργασίας είναι να μελετηθεί και να αναλυθεί η ψηφιακή κοινότητα προγραμματιστών GiHub, μέσα απ' τη χρήση και την αλληλεπίδραση μαζί του.  
Η ιστοσελίδα περιλαμβάνει γενικές πληροφορίες σχετικά με τα ενδιαφέροντα και τις δεξιότητες μου, το βιογραφικό μου αλλά 
και καθημερινές ενημερώσεις που αφορούν θέματα του ενδιαφέροντός μου.

------------------------------------

Τρόπος δημιουργίας ιστοσελίδας
------------------------------------

<p>Η ιστοσελίδα αυτή κατασκευάστηκε χρησιμοποιόντας τον automatic page generator του GitHub. 
Αφού πρώτα δημιουργήθηκε το κατάλληλο repository στο account του GitHub με το κατάλληλο όνομα (tsakof.github.io),
στη συνέχεια μέσα απ' τις επιλογές settings/automatic page generator ξεκίνησε η διαδικασία δημιουργίας του site βάση του έτοιμου GitHub Layout "Architect".</p>
<p>Ο page generator παρήγαγε αυτόματα στο tsakof.github.io repository τα απαραίτητα html,css και Javascript αρχεία και φακέλους ούτως ώστε να δημιουργηθεί και να είναι λειτουργική μια αρχική μορφή της ιστοσελίδας.
Το συγκεκριμένο layout όμως περιελάμβανε μόνο μία σελίδα περιορίζοντας τις δυνατότητες του site.
Έτσι για τη δημιουργία επιπλέον σελίδων δημιουργήθηκαν 3 επιπλέον φάκελοι: About, CV, Blog που ο καθένας περιελάμβανε κι ένα index.html αρχείο.</p>
Για να είναι δυνατή η πρόσβαση σ' αυτές τις σελίδες μέσα απ' την αρχική σελίδα του site ήταν απαραίτητο να δημιουργηθούν κάποια links που θα παρέπεμπαν σ' αυτές .
Έτσι φτιάχτηκαν 4 nav buttons στη κεφαλίδα της αρχικής σελίδας του site: home, about, cv, blog, εισάγοντας στο header του tsakof.github.io/index.html τις εξής γραμμές (25 έως 32):
       <p> <textarea disabled> <nav> </textarea> </p>
<p>	<textarea disabled>  <ul> </textarea></p>
 <p>  <textarea disabled> 		<li><a href="/">Home</a></li> </textarea></p>
 <p>  <textarea disabled>	        <li><a href="/about">About</a></li> </textarea></p>
 <p>  <textarea disabled>	       	<li><a href="/CV">CV</a></li> </textarea></p>
 <p>  <textarea disabled>	        <li><a href="/blog">Blog</a></li> </textarea></p>
<p><textarea disabled>	    </ul> </textarea> </p>
<p><textarea disabled>	</nav> </textarea></p>

Ενώ για να διαμορφωθεί το συγκεκριμένο μενού και να γίνει ομοιόμορφο με το υπόλοιπο site στο αρχείο stylesheets/stylesheet.css εισήχθησαν οι παρακάτω γραμμές κώδικα (γραμμή 449 έως 469):
<p>nav a { color: #ffffff;</p>
  <p>  text-decoration:none;}</p>
    
<p>nav ul, footer ul {</p>
 <p>   font-family:'Architects Daughter', 'Helvetica Neue',  Helvetica, Arial, serif;</p>
   <p> padding: 0px;</p>
  <p>  list-style: none;</p>
  <p>  font-weight: bold;</p>
  <p>  font-size: 1.5em;</p>
  <p>  margin-bottom: 20px;}</p>
<p>nav ul li, footer ul li {</p>
 <p>   display: inline;</p>
 <p>   margin-right: 20px;</p>
 <p>   margin-bottom: 20px;</p>
    <p>color: #ffffff;</p>
   <p> text-decoration:none}</p>
   
Χρησιμοποιώντας το jekyll
---------------------------------------------------------

<p>Το jekyll είναι ένας τρόπος να αναπαράγουμε εύκολα και γρήγορα στατικές σελίδες ενός site  χωρίς να χρειάζεται να επαναλαμβάνουμε τον ίδιο κώδικα σε κάθε μια απ' αυτές. Αυτό επιτυγχάνεται δημιουργώντας ένα συγκεκριμένο layout σε κάποιο φάκελο και στη συνέχεια το "καλούμε" σε όποια σελίδα θέλουμε να το χρησιμοποιήσουμε.</p>
<p>Στη δικιά μας περίπτωση δημιουργήσαμε ένα φάκελο για να αποθηκεύουμε τα layouts μας (_Layouts). Εκεί φτιάξαμε το αρχείο Archtect.html το οποίο περιέχει το βασικό κώδικα της σελίδας μας χωρίς φυσικά το περιεχόμενο. Στα σημεία που θα θέλουμε να τοποθετήσουμε το δικό μας περιεχόμενο χρησιμοποιούμε τα λεγόμενα liquid taqs στα κατάλληλα σημεία π.χ.    {{ content }} και {{ page.title }}</p>
<p>Στην συνέχεια στο αρχείο index.html της κάθε σελίδας μας αντί να αναπαράγουμε το πλήρη html κώδικα καλούμε το jekkyll να επεξεργαστεί το αρχείο μας με τη χρήση κάποιων γραμμών απλού κειμένου στην αρχή του αρχείου                ( front-matter). π.χ.:</p>
<p>---</p>
<p>Layout: Architect</p>
<p>title: about</p>
<p>---</p>
Έτσι ο βασικός κώδικας αναπαράγεται αυτόματα ενώ το περιεχόμενο που τοποθετούμε σε κάθε σελίδα αντικαθιστά τα liquid taqs του Layout Architect.











