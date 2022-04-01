#include <stdio.h>
#include <stdlib.h>
#include <allegro5/allegro.h>
#include <allegro5/allegro_font.h>
#include <allegro5/allegro_primitives.h>
#include <allegro5/allegro_ttf.h>
#include <allegro5/allegro_native_dialog.h>

void fill(int t[4][4]) //tworzenie tablicy
{
    for (int i = 0; i < 4; i++)
    {
        for (int j = 0; j < 4; j++)
        {
            t[i][j] = 0;
        }
    }

}


void print(int t[4][4])  //wypisz tablice
{
    for (int i = 0; i < 4; i++)
    {
        for (int j = 0; j < 4; j++)
        {
            printf("%d  ", t[i][j]);
        }
        printf("\n");

    }printf("\n");
}

void random_2(int t[4][4])
{
    srand(time(0));
    int r1 = 0;
    int r2 = 0;
    int r3 = 0;
    int r4 = 0;

    r1 = rand() % 4;
    r2 = rand() % 4;
    r3 = rand() % 4;
    r4 = rand() % 4;
    t[r1][r2] = 2;
    t[r3][r4] = 2;


    while (r1 == r3 && r2 == r4) //wczesniej wylosowaly sie te same wspolrzedne
    {
        t[r3][r4] = 0;
        r3 = rand() % 4;
        r4 = rand() % 4;
        t[r3][r4] = 2;
    }


}




int main()
{


    int t[4][4];
    fill(t);
    random_2(t);
    print(t);

    
    /* Zmienna do odebrania wskaźnika ekranu */
    if (!al_init())
    {
        fprintf(stderr, "Failed to initialize allegro!\n");
        return -1;
    }
    
    al_init_font_addon();
    al_init_ttf_addon();
    ALLEGRO_DISPLAY* display = NULL;
    ALLEGRO_FONT* fontWYNIK = al_create_builtin_font();
    ALLEGRO_FONT* fontWART_WYNIK = al_create_builtin_font();

    ALLEGRO_FONT* F1 = al_create_builtin_font();
    ALLEGRO_FONT* F2 = al_create_builtin_font();
    ALLEGRO_FONT* F3 = al_create_builtin_font();
    ALLEGRO_FONT* F4 = al_create_builtin_font();
    ALLEGRO_FONT* F5 = al_create_builtin_font();
    ALLEGRO_FONT* F6 = al_create_builtin_font();
    ALLEGRO_FONT* F7 = al_create_builtin_font();
    ALLEGRO_FONT* F8 = al_create_builtin_font();
    ALLEGRO_FONT* F9 = al_create_builtin_font();
    ALLEGRO_FONT* F10 = al_create_builtin_font();
    ALLEGRO_FONT* F11 = al_create_builtin_font();
    ALLEGRO_FONT* F12 = al_create_builtin_font();
    ALLEGRO_FONT* F13 = al_create_builtin_font();
    ALLEGRO_FONT* F14 = al_create_builtin_font();
    ALLEGRO_FONT* F15 = al_create_builtin_font();
    ALLEGRO_FONT* F16 = al_create_builtin_font();
    /* Inicjalizacja biblioteki */
   
    
    if (!al_init_primitives_addon()) 
    {
        fprintf(stderr, "Couldn't initialize primitives addon!\n");
        return -1;
    }

    /* Tworzymy okno, odbieramy wskaźnik, sprawdzamy zwrot */
    display = al_create_display(640, 480);
    if (!display)
    {
        fprintf(stderr, "Failed to create display!\n");
        return -1;
    }
    
    /* Czyścimy ekran kolorem a następnie wyświetlamy zmiany */
   //al_clear_to_color(al_map_rgb(20, 100, 150));
   // al_flip_display();

    al_draw_line(3, 0, 3, 203, al_map_rgb(255, 255, 255), 3);
    al_draw_line(53, 0, 53, 203, al_map_rgb(255, 255, 255), 3);
    al_draw_line(103, 0, 103, 203, al_map_rgb(255, 255, 255), 3);
    al_draw_line(153, 0, 153, 203, al_map_rgb(255, 255, 255), 3);
    al_draw_line(203, 0, 203, 203, al_map_rgb(255, 255, 255), 3);
    
    
    
    
    al_draw_line(3, 0, 203, 0, al_map_rgb(255, 255, 255), 3);
    al_draw_line(3, 53, 203, 53, al_map_rgb(255, 255, 255), 3);
    al_draw_line(3, 103, 203, 103, al_map_rgb(255, 255, 255), 3);
    al_draw_line(3, 153, 203, 153, al_map_rgb(255, 255, 255), 3);
    al_draw_line(3, 203, 203, 203, al_map_rgb(255, 255, 255), 3);
    
    al_draw_text(fontWYNIK,al_map_rgb(255,255,255),250,30,0,"WYNIK:");
    
 
            al_draw_textf(F1, al_map_rgb(255, 255, 255), 25, 25, 0, "%d",t[0][0]);
            al_draw_textf(F2, al_map_rgb(255, 255, 255), 75, 25, 0, "%d", t[0][1]);
            al_draw_textf(F3, al_map_rgb(255, 255, 255), 125, 25, 0, "%d", t[0][2]);
            al_draw_textf(F4, al_map_rgb(255, 255, 255), 175, 25, 0, "%d", t[0][3]);

            al_draw_textf(F5, al_map_rgb(255, 255, 255), 25, 75, 0, "%d", t[1][0]);
            al_draw_textf(F6, al_map_rgb(255, 255, 255), 75, 75, 0, "%d", t[1][1]);
            al_draw_textf(F7, al_map_rgb(255, 255, 255), 125, 75, 0, "%d", t[1][2]);
            al_draw_textf(F8, al_map_rgb(255, 255, 255), 175, 75, 0, "%d", t[1][3]);

            al_draw_textf(F9, al_map_rgb(255, 255, 255), 25, 125, 0, "%d", t[2][0]);
            al_draw_textf(F10, al_map_rgb(255, 255, 255), 75, 125, 0, "%d", t[2][1]);
            al_draw_textf(F11, al_map_rgb(255, 255, 255), 125, 125, 0, "%d", t[2][2]);
            al_draw_textf(F12, al_map_rgb(255, 255, 255), 175, 125, 0, "%d", t[2][3]);

            al_draw_textf(F13, al_map_rgb(255, 255, 255), 25, 175, 0, "%d", t[3][0]);
            al_draw_textf(F14, al_map_rgb(255, 255, 255), 75, 175, 0, "%d", t[3][1]);
            al_draw_textf(F15, al_map_rgb(255, 255, 255), 125, 175, 0, "%d", t[3][2]);
            al_draw_textf(F16, al_map_rgb(255, 255, 255), 175, 175, 0, "%d", t[3][3]);
      
    al_flip_display();






    /* Czekamy chwile, niszczymy ekran i kończymy program */
    al_rest(10000);
    al_destroy_display(display);


   

    return 0;
}
