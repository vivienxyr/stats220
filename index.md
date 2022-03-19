# Hello there!
Welcome to my Stats220 website!

For our first assignment in my [Statistics220](https://courseoutline.auckland.ac.nz/dco/course/STATS/220/1223) course at the University of Auckland, we were instructed to create a meme on RStudio. 

*My inspiration for my meme incudes:*

<!--- unordered lists --->
* My unability to pick **one meme** format 
* My wish to include all **three** formats in the meme
* The challenge to find the original image of each meme 

Although there were certainly many learning curves in the process of creating this meme, I am proud to present the finished product.


![my_meme](https://user-images.githubusercontent.com/100745431/159103305-96ad46dd-5acf-4317-996c-39083114baef.png)

**R Code**

```
library(magick)

# square one 
drake_image <- image_read("https://images.thestar.com/content/dam/thestar/life/fashion_style/2015/11/07/drakes-hotline-bling-coat-a-winter-fashion-sensation/drake-coat-hotline-bling.jpg") %>% 
  image_scale(500)

# square two 
drake_text <- image_blank(width = 450,
                          height = 200, 
                          color = "#FDFEFE") %>%
  image_annotate(text = "Choosing the Drake format \nfor my Statistics \nassignment",
                 color = "#000000",
                 size = 30, 
                 font = "Times",
                 gravity = "center")

# square three
expandingbrain_image <- image_read("https://nestheprint.com/wp-content/uploads/2020/05/3.jpg") %>%
  image_scale(500)

# square four 
expandingbrain_text <- image_blank(width = 450,
                                   height = 200, 
                                   color = "#FDFEFE") %>%
  image_annotate(text = "Choosing the Expanding Brain \nformat for my Statistics \nassignment ",
                 color = "#000000",
                 size = 30, 
                 font = "Times",
                 gravity = "center")

# square five 
pooh_image <- image_read("https://uploads.dailydot.com/2019/04/winnie-the-pooh.jpg?auto=compress&fm=pjpg&ixlib=php-3.3.0") %>%
  image_scale(500)

# square six 
pooh_text <- image_blank(width = 450,
                         height = 200, 
                         color = "#FDFEFE") %>%
  image_annotate(text = "Choosing the Pooh format \nfor my Statistics \nassignment",
                 color = "#000000",
                 size = 30, 
                 font = "Times",
                 gravity = "center")

# square seven 
final_image <- image_read("https://i.kym-cdn.com/entries/icons/mobile/000/020/147/drake.jpg") %>%
  image_scale(500)


# square eight 
final_text <- image_blank(width = 450,
                          height = 200, 
                          color = "#FDFEFE") %>%
  image_annotate(text = "Using all three formats for \nthe ultimate crossover meme \nfor my Statistics assignment",
                 color = "#000000",
                 size = 30, 
                 font = "Times",
                 gravity = "center")

# using vectors
first_row <- image_append(c(drake_image, drake_text ))

second_row <- image_append(c(expandingbrain_image, expandingbrain_text))

third_row <- image_append(c(pooh_image, pooh_text))

fourth_row <- image_append(c(final_image, final_text))

# combining 

meme <- c(first_row, second_row, third_row, fourth_row) %>%
  image_append(stack = TRUE) %>%
  image_scale(800)

image_write(meme, "my_meme.png")
```
**This is was made using the R package [{magick}](https://cran.r-project.org/web/packages/magick/vignettes/intro.html).** 



