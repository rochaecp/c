# C - Strings

- C strings are character vectors.
- The last character is '\0'.
- 'a' == character, "a" == string.

~~~c
char name[15] = "Mauricio";         
char name[15] = {'A', 'n', 'a'}; 
char name[] = {'A', 'n', 'a'};                            // size == 4
char name[15]; scanf ("%s", name);                    // input string - without spaces
char names[2][50] = {"Mauricio", "Joana"} ; 
printf ("%s\n", names[1]); // print Joana

/* lib: string.h */
char myChar = getchar();            // input string - with spaces
gets (name);                                    // char name[15];
puts ("ok\n");             
strcpy (name, "Mauricio");     
strcpy (strDest, strOrigem); 
strcat (name, " Barbosa");     
int tam = strlen (name);         
strcmp (s1, s2);                             // if s1 == s2 -> 0, if s1 > s2 -> 1, if s1 < s2 -> -1
strstr (phrase, word)                    // true if phrase contains word

/* Ex.: strcmp */
if (!strcmp (name, "Mauricio")
    printf ("Ok\n");
else
    puts ("not Ok\n");

/* Ex.: strtok */
#include <stdio.h>
#include <string.h>
int main()
{
    char txt[] = {"Phrase1#Phrase2#Phrase3#"};
    printf ("%s\n", strtok (txt, "#");    
    printf ("%s\n", strtok (NULL, "#");
    printf ("%s\n", strtok (NULL, "#");
    return 0;
}
~~~