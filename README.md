# 	1.In functie de atributele viewport-ului,randarea triunghiului se va schimba.Valoarea constantei MatrixMode.Projection 
nu poate fi modificata in OpenTK.

3.1)Un viewport este o fereastra prin care este vizualizată o parte a scenei 3D în cadrul unei aplicații. Este o regiune a ferestrei
 de afișare în care sunt proiectate și afișate obiectele 3D sau scenele. 

2)Conceptul de "frames per second" (FPS) în contextul bibliotecii OpenGL se referă la numărul de cadre (imagini) care sunt afișate pe
 ecran într-o secundă de către aplicația grafică OpenGL.

3)Metoda OnUpdateFrame() este apelată în fiecare cadru (frame) al aplicației. Această metodă este destinată pentru gestionarea logicii
 de actualizare a scenei sau a stării jocului și este apelată înainte de desenarea fiecărui frame.

4)Modul imediat de randare este un mod tradițional de utilizare a OpenGL în care programatorul
 specifică direct comenzile grafice pentru fiecare obiect sau efect pe care dorește să îl deseneze pe ecran.

5)OpenGL a eliminat suportul pentru modul imediat începând cu versiunea OpenGL 3.0 și ulterior. Prin urmare,
 versiunile mai recente ale OpenGL, cum ar fi OpenGL 3.x, OpenGL 4.x și OpenGL 4.6, nu mai acceptă modul imediat.

6)După ce s-a terminat actualizarea logicii în metoda OnUpdateFrame(), se apelează metoda OnRenderFrame(). În această metodă, programatorul
 implementează codul pentru desenarea sau randarea scenei 3D utilizând funcțiile OpenGL. Este locul în care se definesc și se trimit comenzile
 grafice către GPU pentru a desena obiectele.

7)Recalcularea viewport-ului,ajustarea matricei de proiecție,evitarea distorțiilor,actualizarea aspectului vizual.

8)
---'fieldOfView': reprezintă unghiul de vizualizare al camerei, adesea exprimat în radiani. Este unghiul de deschidere al piramidei de vizualizare
 și controlează câmpul de vedere al camerei.

---'aspectRatio':reprezintă raportul dintre lățimea și înălțimea ferestrei de afișare. Este de obicei calculat ca width / height.

---'nearPlane':reprezintă distanța de la ochiul virtual la planul de față al volumului de vizualizare.

---'farPlane':reprezintă distanța de la ochiul virtual la planul de spate al volumului de vizualizare.


LABORATOR 9
1) Texturarea imaginilor cu transparență și fără aceasta poate duce la diferențe semnificative în modul în care textura este afișată pe obiectele 3D.
2) OpenGL acceptă o varietate de formate de imagine pentru texturare. Câteva dintre cele mai comune formate de imagine utilizate în procesul de texturare în OpenGL includ:
   a)BMP(bitmap)
   b)PNG
   c)JPEG
   d)TGA
3)Când se modifică culoarea unui obiect texturat prin manipularea canalelor RGB, se produce o schimbare în modul în care culorile texturii sunt aplicate pe obiect. Culoarea obiectului va fi rezultatul combinației dintre culoarea originală a texturii și culorile modificate ale canalelor RGB.
4)Când este activata iluminarea într-o scenă cu obiecte texturate în OpenGL, se vor produce mai multe efecte și schimbări în modul în care obiectele sunt vizualizate în comparație cu o scenă în care iluminarea este dezactivată. Iată câteva diferențe semnificative:

a)Interacțiunea cu lumina ambientală:

--Iluminare activată: Obiectele texturate vor interacționa cu lumina ambientală, adică vor reflecta o parte a luminii ambientale a mediului.
--Iluminare dezactivată: Obiectele texturate vor avea culorile texturii lor, dar nu vor avea reflexii ale luminii ambientale.
b)Calculul culorilor difuze și specular:

--Iluminare activată: Se va realiza un calcul al culorilor difuze și specular în funcție de direcția luminii și orientarea obiectelor față de lumină.
--Iluminare dezactivată: Nu se vor lua în considerare difuziunea și reflexiile speculare, iar obiectele vor avea culorile texturii fără aceste efecte.
c)Aspectul tridimensional al obiectelor:

--Iluminare activată: Obiectele texturate vor avea un aspect mai tridimensional, cu umbre și lumini care se schimbă în funcție de direcția luminii.
--Iluminare dezactivată: Obiectele pot părea mai plate, fără efecte de umbră și lumini difuze.
d)Impactul asupra performanței:

--Iluminare activată: Calculul iluminării poate avea un impact semnificativ asupra performanței, deoarece implică calcule complexe pentru fiecare pixel.
--Iluminare dezactivată: Fără iluminare, performanța poate fi îmbunătățită, deoarece se evită calculul costisitor al iluminării.


LABORATOR 11
1)Comenzile GL.Push() și GL.Pop() sunt folosite pentru a manipula stiva matricilor în OpenGL și sunt adesea utilizate împreună pentru a izola modificările matricelor într-o anumită porțiune de cod. Rolul lor principal este de a salva și de a restaura starea matricei curente.Este necesară utilizarea GL.Push() atunci când se dorește păstrarea stării actuale a matricei (cum ar fi modelview sau proiecție) într-un anumit punct al codului. Acest lucru este util atunci când se efectuează transformări specifice într-o porțiune de cod și se dorește revenirea la starea anterioară după finalizarea acestora.Utilizarea GL.Pop() este necesară pentru a reveni la starea matricei anterioare salvată. Fără aceasta, modificările efectuate asupra matricelor într-o anumită porțiune de cod ar afecta întreaga aplicație sau scenă, ceea ce poate duce la rezultate nedorite.

2)Metodele GL.Rotate(), GL.Translate() și GL.Scale() sunt folosite pentru a efectua transformări asupra matricelor în OpenGL, influențând astfel modul în care obiectele sunt afișate pe ecran.
a)GL.Rotate():
          // Rotirea unui obiect cu un unghi dat în jurul axei Y
          GL.Rotate(45.0, 0.0, 1.0, 0.0);
b)GL.Translate():
           // Translatarea unui obiect la dreapta pe axa X și în sus pe axa Y
           GL.Translate(2.0, 1.0, 0.0);
c)GL.Scale():
           // Scalarea unui obiect cu un factor de 2 pe axa X și de 0.5 pe axa Y
           GL.Scale(2.0, 0.5, 1.0);

3)Numărul de niveluri de manipulări ierarhice (folosind GL.Push() și GL.Pop()) pe care o scenă OpenGL le suportă este determinat de stiva de matrici OpenGL. Această stivă este folosită pentru a gestiona transformările și alte proprietăți ale matricilor în OpenGL.
Stiva OpenGL poate să aibă o limită maximă de niveluri, iar această limită poate varia în funcție de implementarea OpenGL și de specificațiile hardware. În practică, majoritatea implementărilor OpenGL moderne permit un număr semnificativ de niveluri de manipulări ierarhice. În general, este suficient pentru majoritatea scenelor 3D obișnuite.
