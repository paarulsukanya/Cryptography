//Columnar Transposition

#include &lt;iostream&gt;

#include&lt;stdio.h&gt;

#include&lt;string.h&gt;

#include&lt;ctype.h&gt;

using namespace std;

void encrypt()

{

char str[100];

cout &lt;&lt; &quot;\nEnter plain text&quot;;

cin &gt;&gt; str;

char key[100],backup[100];

cout &lt;&lt; &quot;\nEnter key&quot;;

cin &gt;&gt; key;

strcpy_s(backup, key);

int s = strlen(str);

int k = strlen(key);

cout &lt;&lt; &quot;Length of plain text = &quot; &lt;&lt; s &lt;&lt; endl &lt;&lt; &quot;Length of key = &quot; &lt;&lt; k;

int offset = s%k;

//adding fillers

if (offset)

{

for (int i = 0; i&lt;k-offset; i++)

{

strcat_s(str,&quot;x&quot;);

}

}

cout &lt;&lt; endl &lt;&lt; str &lt;&lt; endl;

s = strlen(str);

//calculating number of rows

int row = s / k;

char temp[100][100];

int z = 0;

//writing into temporary character array row-wise

for (int i = 0; i &lt; row; i++)

{

for (int j = 0; j &lt; k; j++)

{

temp[i][j] = str[z++];

cout &lt;&lt; temp[i][j];

}

}



//sorting key

char t;

for (int i = 0; i &lt; k; i++)

{

for (int j = 0; j &lt; k - 1; j++)

{

if (key[i] &lt; key[j])

{

t = key[i];

key[i] = key[j];

key[j] = t;

}

}

}

//finding the pattern of decryption

int pattern[10];

for (int i = 0; i&lt;k; i++)

{

int j = 0;

while (j != k)

{

if (backup[i] == key[j])

{

pattern[j] = i;

break;

}

else

j = j + 1;

}

}

cout &lt;&lt; &quot;\nThe pattern in which the text has to be encrypted is as follows: &quot;;

for (int i = 0; i&lt;k; i++)

cout &lt;&lt; pattern[i] &lt;&lt; &quot; &quot;;

cout &lt;&lt; &quot;\n&quot;;



char cipher[100][100];



for (int i = 0; i &lt; k; i++)

{

for (int j = 0; j &lt; row; j++)

{

cipher[i][j] = temp[j][pattern[i]];

}

}

cout &lt;&lt; endl &lt;&lt; &quot;Encrypted Text\n&quot;;

for (int i = 0; i &lt;k; i++)

{

for (int j = 0; j &lt; row; j++)

cout &lt;&lt; cipher[i][j];

}



cout &lt;&lt; endl;

}

void decrypt()

{

char key[10], cipher[10][10], backup[10], cback[10][10];

int k, c, m;

//key

cout &lt;&lt; &quot;\nEnter the key length &quot;;

cin &gt;&gt; k;

cout &lt;&lt; &quot;\nEnter the key &quot;;

for (int i = 0; i&lt;k; i++)

cin &gt;&gt; key[i];

for (int i = 0; i&lt;k; i++)

backup[i] = key[i];

//cipher

cout &lt;&lt; &quot;\nEnter the cipher text length &quot;;

cin &gt;&gt; c;

m = c / k;

cout &lt;&lt; &quot;\nEnter the cipher text without spaces\n&quot;;

for (int j = 0; j&lt;k; j++)

for (int i = 0; i&lt;m; i++)

cin &gt;&gt; cipher[i][j];

cout &lt;&lt; &quot;\nThe cipher text entered is as follows : &quot;;

for (int i = 0; i&lt;m; i++)

{

cout &lt;&lt; &quot;\n&quot;;

for (int j = 0; j&lt;k; j++)

{

cout &lt;&lt; cipher[i][j] &lt;&lt; &quot; &quot;;

}

}

//sorting key

char t;

int i, j;

for (i = 0; i&lt;k; i++)

{

for (j = 0; j&lt;k - 1; j++)

{

if (key[i]&lt;key[j])

{

t = key[i];

key[i] = key[j];

key[j] = t;

}

}

}

cout &lt;&lt; &quot;\nThe sorted key is: &quot;;

for (int i = 0; i&lt;k; i++)

cout &lt;&lt; key[i];

cout &lt;&lt; &quot;\n&quot;;

//finding the pattern of decryption

int pattern[10];

for (int i = 0; i&lt;k; i++)

{

int j = 0;

while (j != k)

{

if (backup[i] == key[j])

{

pattern[i] = j;

break;

}

else

j = j + 1;

}

}

cout &lt;&lt; &quot;\nThe pattern in which the text has to be decrypted is as follows: &quot;;

for (i = 0; i&lt;k; i++)

cout &lt;&lt; pattern[i] &lt;&lt; &quot; &quot;;

cout &lt;&lt; &quot;\n&quot;;

//rearranging the cipher matrix according to pattern

for (i = 0; i&lt;m; i++)

{

for (j = 0; j&lt;k; j++)

{

cback[i][j] = cipher[i][pattern[j]];

}

}

/*

cout&lt;&lt;&quot;\nThe rearranged matrix is as follows &quot;;

for(i=0;i&lt;m;i++)

{

cout&lt;&lt;&quot;\n&quot;;

for(j=0;j&lt;k;j++)

{

cout&lt;&lt;cback[i][j]&lt;&lt;&quot; &quot;;

}

}

*/

cout &lt;&lt; &quot;\nThe plain text without spaces is as follows:\n &quot;;

for (i = 0; i&lt;m; i++)

for (j = 0; j&lt;k; j++)

cout &lt;&lt; cback[i][j];

}

int main()

{

int x;

lbl:

cout &lt;&lt; &quot;\nMultiple Columnar Transposition&quot;;

cout &lt;&lt; &quot;\nPlease enter your choice &quot;;

cout &lt;&lt; &quot;\n1.Encrpyt\n2.Decrypt\n3.Exit&quot;;

cin &gt;&gt; x;

switch (x)

{

case 1: encrypt();

break;

case 2: decrypt();

break;

case 3: exit(0);

default: cout &lt;&lt; &quot;\nInvalid input!&quot;;

}

goto lbl;

return 0;

}
