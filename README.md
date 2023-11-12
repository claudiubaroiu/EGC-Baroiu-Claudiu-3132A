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
