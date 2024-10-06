## README

# Sistem de Management al Universității în Python

Acest proiect este un sistem bazat pe Python pentru gestionarea unei universități, care include facultăți și studenți. Sistemul permite înscrierea studenților în facultăți, absolvirea studenților și căutarea facultății din care face parte un student.

## Funcționalități
- Crearea și gestionarea facultăților din cadrul unei universități.
- Înscrierea studenților în diverse facultăți.
- Absolvirea studenților și urmărirea stării lor (înscris sau absolvent).
- Afișarea unei liste cu studenții înscriși și absolvenți pentru fiecare facultate.
- Găsirea facultății unui student pe baza ID-ului acestuia.
- Afișarea tuturor facultăților sau filtrarea facultăților după domeniul de studiu.

## Structura Proiectului

Componentele principale ale sistemului sunt implementate în trei clase:

1. **Student**: Reprezintă un student individual cu atribute precum nume, ID student, email și statusul absolvirii.
2. **Faculty**: Reprezintă o facultate cu un anumit domeniu de studiu și gestionează o listă de studenți.
3. **University**: Gestionează mai multe facultăți și oferă operațiuni pentru afișarea și căutarea facultăților.

### Clase și Metode

#### 1. Clasa `Student`
- **Atribute**:
  - `name`: Numele studentului.
  - `student_id`: ID-ul unic al studentului.
  - `email`: Adresa de email a studentului.
  - `is_graduated`: Boolean care indică dacă studentul a absolvit sau nu.

- **Metode**:
  - `graduate()`: Marchează studentul ca absolvent.
  - `__str__()`: Returnează o descriere formatată a detaliilor studentului, inclusiv statusul absolvirii.

#### 2. Clasa `Faculty`
- **Atribute**:
  - `name`: Numele facultății.
  - `field`: Domeniul de studiu al facultății (ex.: Informatică, Inginerie).
  - `students`: Lista de studenți înscriși în facultate.

- **Metode**:
  - `enroll_student(student)`: Adaugă un student în facultate.
  - `graduate_student(student_id)`: Marchează un student ca absolvent pe baza ID-ului său.
  - `get_current_students()`: Returnează lista cu studenți care sunt încă înscriși (neabsolvenți).
  - `get_graduates()`: Returnează lista cu studenți care au absolvit.
  - `student_in_faculty(student_id)`: Verifică dacă un student face parte din facultate, pe baza ID-ului său.
  - `__str__()`: Returnează o descriere formatată a facultății și a numărului de studenți.

#### 3. Clasa `University`
- **Atribute**:
  - `name`: Numele universității.
  - `faculties`: Lista facultăților din universitate.

- **Metode**:
  - `create_faculty(name, field)`: Creează o nouă facultate și o adaugă în universitate.
  - `find_student_faculty(student_id)`: Găsește facultatea din care face parte un student pe baza ID-ului său.
  - `display_faculties()`: Afișează detaliile tuturor facultăților din universitate.
  - `display_faculties_by_field(field)`: Afișează facultățile care corespund unui anumit domeniu de studiu.

## Utilizare

1. Rulați scriptul, iar utilizatorul va fi solicitat să introducă numele universității, facultățile și studenții.

2. Pentru fiecare facultate, furnizați:
   - Numele facultății
   - Domeniul de studiu

3. Pentru fiecare student, furnizați:
   - Numele studentului
   - ID-ul studentului
   - Adresa de email
   - Facultatea în care se va înscrie

4. Sistemul permite:
   - Absolvirea unui student pe baza ID-ului său.
   - Afișarea studenților înscriși și absolvenți dintr-o facultate.
   - Găsirea facultății din care face parte un student, pe baza ID-ului.
   - Afișarea tuturor facultăților sau căutarea facultăților pe baza domeniului de studiu.

## Exemplu

```bash
Enter the name of the university: Universitatea Tehnica a Molodvei
Enter the number of faculties: 2
Enter faculty name: Calculatoarea Informatica si Microelectronica
Enter field of study: Tehnologii Informationale
Enter faculty name: Inginerie Mecanica, Industriala si de Transport
Enter field of study: Constructoare de Masini
Enter the number of students: 2
Enter student name: Ababii Ionel
Enter student ID: 2004123456789
Enter student email: johnny@gmail.com
Choose a faculty by number (0 to 1): 0
Enter student name: Fiorosu Armando
Enter student ID: 2004987654321
Enter student email: hulk@gmail.com
Choose a faculty by number (0 to 1): 1
Enter the student ID to graduate: 2004123456789
Student Ababii ionel has graduated.

Current students in Computer Science:
Student: Ababii ionel, ID: 2004123456789, Email: johnny@gmail.com, Status: Graduated

Graduates in Computer Science:
Student: Ababii ionel, ID: 2004123456789, Email: johnny@gmail.com, Status: Graduated

Enter student ID to find their faculty: 2004987654321
Student 2004987654321 belongs to: Constructoare de Masini

All Faculties:
Faculty: Calculatoarea Informatica si Microelectronica , Field: Tehnologi Infromationale, Total Students: 1
Faculty: Inginerie Mecanica, Industriala si de Transport, Field: Constructoare de Masini, Total Students: 1

Enter a field to search for faculties: Constructoare de Masini

Faculties in Constructoare de Masini:
Faculty: Inginerie Mecanica, Industriala si de Transport, Field: Constructoare de Masini, Total Students: 1
```
