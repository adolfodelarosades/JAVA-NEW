# Capítulo 2: ¡Creando un sitio web!

* Inicio del sitio web + Generación de imágenes
* Terminando la Estructura del Sitio Web
* Creando varias páginas
* Introducción a JavaScript: Cómo hacer que el sitio web sea interactivo
* Aplicación de JavaScript: desplazamiento suave y control deslizante de imágenes
* Cómo conectar un formulario de contacto a una base de datos

## Inicio del sitio web + Generación de imágenes

Start of the Website + Generating Images

In this lesson, you will learn to create a basic demo website as a freelancer that designs websites using AI. We will instruct ChatGPT to write code for us with whatever basic features and design we want on the webpage.

Hi, Veron, welcome to the next lesson. So I thought it would be fun if the website we were actually going to make using this chatgpt A, I would be a website where we offer our services as a freelancer that makes websites very fast using A I assistance. So you all are immediately able to start your freelancing business once you're done with this course, which you know, you can thank me later for that.

So let's first look at what such a freelancing website would actually look like so that we are able to ask chatgpt a precise question about what it has to create for us. So let's quickly go to Google and let's type in design of a personal freelancer website and let's go to images and see what it says.

Alright, so let's scroll through this a little bit. It looks like most of these start with a big picture of the person themselves with a small introduction about what they do. And then typically it looks like it is followed by an about section. So a slightly longer introduction about what they offer and who they are.

So I think we can start with that. So let's go to Chatgpt. So I'm going to ask it, give me the HTML code for a website within the header, a big picture on the right and on the left, the title of a freelance web designer, a two line introduction of the A I assisted web design services I offer and a call to action below the header. I want an about section that introduces me and my service in about 200 words. And let's see what it gives us. All right. So it gave us the title freelance web designer.

And apparently we are specialized in creating modern websites. And it also wrote us this 200 words paragraph and it left blank spaces that we can fill in our own name, our own location and our number of years of experience within this industry, which is very nice.

And so let's copy this whole code and actually instead of selecting it all and hit control C, you can also just go to the top right, right here and click copy code. There we go. All right. So now here back in visual studio, we can just delete this code that we have right here and paste this new code right over it. And then we can hit control s to save this file and then we can right mouse, click right here and go to the preview in the browser and let's see what this looks like. All right. So as you can see this still looks quite ugly, but of course, we haven't used any CSS code yet. And CSS is the layer on top of HTML that we can use to change this appearance. So to get some CSS codes for this HTML code, we can simply go back to Chatgpt and now also provide some accompanying CSS codes to make the website look beautiful and modern. And let's see what it gives us. All right. So it looks like it gave us a website with a dark background and white text. And it also changed some oral things like the font and the font size.

So let's just copy this code and then let's go back to visual studio and now we actually have to put the CSS code in a new file. So let's go to the top left here and hit new file and let's make that CSS codes dot CSS and let's hit enter and now we have this new file and it knows this has to be a CSS file because we put the extension dot CSS behind it. And now let's just paste the CSS code we just copied in this file. There we go. And then let's hit control s and then let's go to the preview in the browser to see what this looks like. And as you can see, it still looks the same and nothing changed. And that's because we haven't linked this CSS file to the HTML file. So of course, we could manually add the link to the CSS file in this HTML code, but we can also just ask chatgpt to do it for us. So let's go back to Chatgpt and let's ask it, please provide the HTML code that refers to the HTML file and tell me where I have to place it and let's hit enter and see what it gives us. All right. So it looks like in the head, we have to add this part. So a link to the style sheet and the reference is style dot CSS. And it also says right here, we have to create a file named style dot CSS. So we may have to change the name of our CSS file.

So it looks like from this description, we can just copy this link right here and go to visual studio and right here in the head of our HTML below the title. Let's just paste that right there. And now it refers to style dot CSS. So we have to rename this CSS code file or we can just change this reference to what we called our CSS file, which is CSS code. So it's a TS to save this. And let's now go to the preview in the browser and there we go. So it looks like it gave us a header with a black background and the rest of the website has a white background and it's already starting to look like a nice website.

But one thing I'm missing here is the image and right here it just says header image. So let's go to our visual studio code and let's see where it's created the image. So right here in the HML, we can see this deck that says image source header image dot JPEG. But of course, we don't actually have an image that this is referring to.

So let's get that image. So there are two things we can now do. We could of course upload an image of ourselves to this website, but we can also do something else. So most of you probably know openai company behind chatgpt also created an image generation service. So most of you probably know about Dali where you can generate 50 free images, but you have to pay for it after that. But there's actually also a completely free unlimited version on the open A website. So if we go back to chrome and we type in www dot open dot A I forward slash images and we hit enter, we get this OpenAI image generation page. Now if we go back to the example of freelancing pages, so we want an image, something like this. But A I is very bad at generating actual human faces. So it's better if we create some sort of cartoon or drawing is sort of a persona of the freelancer we want to portray.

So let's go back to the OpenAI image generation websites and with most of these a is it is best to be as specific as possible to get a good output. So let's type in a young creative person with his arms crossed, smiling excitedly with a white background, cartoon, digital art. And let's see what that gives us.

All right. So some of these might be usable, but let's give it one more run and see what comes up. All right. So a lot of these are generating images of Children. So instead of a young creative person, let's just write a creative person and let's hit enter and see what it gives us.

All right. So that's already starting to look a little bit better, but let's give it one more run. All right. So a lot of these are actually smiling a little bit too excitedly, in my opinion. So let's actually change this to smiling excitedly while still looking professional and let's see what that gives us nice. So I think this one looks pretty cool.

So what we can do now is just download it right here and I'm going to place this image in the visual studio code folder that we made. So the folder named my first website. All right. So I went ahead and added that image to the visual studio code folder. And as you can see once we open visual studio code, this image immediately pops up on the top left here with the other files and now we can refer to this image within our code. So if we go to the HTML code right here, that refers to the image in the header, we can just delete this random name that jet GPT gave us and we can just start typing a and visual studio code. As you can see, it is very good at autofilling what we want to type.

So even with one letter, it already knows, I want to refer to the image and I can now just click this or hit enter and there we go. And if we now just hit control s to save this and go to the preview, as you can see this image popped up here perfectly. But I think this will look a little bit nicer here if the background would be transparent and we can actually do that very easily. So there are two websites that I recommend for deleting the background of an image very easily and both of them will be linked in the lesson resources. So the first is remove do BG you can simply drag an image in here and it will remove the background for you as you can see. So you can just immediately freely download the 500 by 500 version of this picture or you can download the HD version, but that's going to cost you credits and you only get a limited amount of credits and beyond that, you will have to pay for them. But since the full size of this image is only 512 by 512 pixels. Anyway, the preview version is going to be pretty close to the final result.

So we might as well just select that one. But before we do that, as you can see right here, there's a little bit that it missed. So we can just click edit and then go to erase, restore and then we get this eraser tool and we can just click right there to make sure that final piece is also deleted and let's download and download image.

So that's the first website that we can use remove dot PG. But there's also another website and that's a service by Adobe. Adobe Express. And if you type into Google, Adobe Express background remover and click the first link, get to this website. And this is a very good, very powerful background remover. And you can also create all these effects as you can see here, but you do have to create an account here. So it will take a little bit longer to set up. But then you have a pretty nice background remover. So if you plan to use this more often and it is quite often used in web design to get transparent backgrounds, I would definitely sign up for Adobe Express. But for now, I'm just going to use the results that remove BG gave us.

So here we are back in visual studio code and I went ahead and added the new removed background image and I deleted the old image with the background. So now let's delete this reference to the previous image and let's start typing again. Let's write a and it will autocomplete and it hit enter and there we go. And as you can see it added this extension to the name, remove BG preview.

So let's again, hit control S to save this and let's go to the preview. And as you can see right there, we have this very nice image avatar right there in our header. All right. So that's it for this lesson. In the next lesson. We are going to work on extending this website and also making it look a little bit more exciting. So I hope to see you in that one.

## Terminando la Estructura del Sitio Web
## Creando varias páginas
## Introducción a JavaScript: Cómo hacer que el sitio web sea interactivo
## Aplicación de JavaScript: desplazamiento suave y control deslizante de imágenes
## Cómo conectar un formulario de contacto a una base de datos
