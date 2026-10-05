1.longeat palindrome 
#include <stdio.h>
#include <string.h>

int isPalindrome(char str[], int start, int end)
{
    while (start < end)
    {
        if (str[start] != str[end])
            return 0;

        start++;
        end--;
    }

    return 1;
}

int main()
{
    char str[100];
    int i, j;
    int maxLength = 1;
    int startIndex = 0;

    printf("Enter a string: ");
    scanf("%s", str);

    int n = strlen(str);

    for (i = 0; i < n; i++)
    {
        for (j = i; j < n; j++)
        {
            if (isPalindrome(str, i, j))
            {
                if (j - i + 1 > maxLength)
                {
                    maxLength = j - i + 1;
                    startIndex = i;
                }
            }
        }
    }

    printf("Longest Palindromic Substring: ");

    for (i = startIndex; i < startIndex + maxLength; i++)
    {
        printf("%c", str[i]);
    }

    return 0;
}



2.Non repeating elements 
#include <stdio.h>

int main()
{
    char str[100];
    int freq[256] = {0};
    int i;
    int found = 0;

    printf("Enter a string: ");
    scanf("%s", str);

    for (i = 0; str[i] != '\0'; i++)
    {
        freq[(unsigned char)str[i]]++;
    }

    for (i = 0; str[i] != '\0'; i++)
    {
        if (freq[(unsigned char)str[i]] == 1)
        {
            printf("First Non-Repeating Character: %c", str[i]);
            found = 1;
            break;
        }
    }

    if (found == 0)
    {
        printf("-1");
    }

    return 0;
}




3.remove duplicate 
#include <stdio.h>

int main()
{
    char str[100];
    int seen[256] = {0};
    int i;

    printf("Enter a string: ");
    scanf("%s", str);

    printf("After removing duplicates: ");

    for (i = 0; str[i] != '\0'; i++)
    {
        if (seen[(unsigned char)str[i]] == 0)
        {
            printf("%c", str[i]);
            seen[(unsigned char)str[i]] = 1;
        }
    }

    return 0;
}
