# About me
![Picture of me](IMG_5782.jpg)
### I am a CSE major at UCSD in my junior year
### I have taken an interest in graphics programming and am taking **CSE 168** this SP25 after taking **CSE 167** in WI25, where I will be studying rendering via ray tracing methods.
### This is inspiration came from watching a youtube channel called [Acerola](https://www.youtube.com/@Acerola_t)

### I've had a Summer internship working at Jove Sciences as a programming assistant where I helped work on software for maritime intellegence purposes.


## Here are some of the languages I've programmed in, (in order of most to least expirience)
1. C/C++
2. Python
3. Java

## Here are some of the classes I've taken:
* Advanced Data Structures
* Algorithm Analysis
* Computer Graphics

### I want to do to graphics programming so these are the plans I have to get there
- [x] Take a UCSD course in Computer Graphics
- [ ] Build my own Ray Tracer with added features implemented from modern algorithms
- [ ] Finish Jasper Flick's Rendering Tutorials
- [ ] Build my own Rasterizer with added features implemented from modern algorithms

## Here's my semi-correct attempt at implrefraction from my Final Project in CSE 167:

```
    vec3 refraction_dir; 
    float random = linearRand(0.0f, 1.0f);
    vec3 normal = intersection.normal;
    vec3 point = intersection.point;
   
    //Test if the intersecting ray is coming from the outside of the model or not.
    int outside = dot(ray.dir,-normal) > 0;
    if (outside) {
        //test if angle of refraction is > 90 degrees(total internal reflection), or if chosen to be specular reflection, either way, reflect
        if (random < shininess ||dot(-1.0f * ((outside * 2) -1) * normal,refraction_dir) < 0 ) {
            // Specular Reflection
            vec3 W_specular = this->specular;

            vec3 reflection_dir = normalize(2 * dot(normal,-ray.dir) * normal + ray.dir);  // TODO: Update with reflection direction

            // update radiance
            ray.W_wip = ray.W_wip * W_specular;
            ray.p0 = point + 0.001f * normal;  // offset point slightly to avoid self intersection
            ray.dir = reflection_dir;
            ray.is_diffuse_bounce = false;
            ray.n_bounces++;

            return ray;
        }
        //Use snells law to refract the light
        refraction_dir = normalize(-normal + (ray.dir + normal) * (1.0f/ior));  // TODO: Update with reflection direction
        ray.p0 = point + 0.001f * (-normal);  // offset point slightly to avoid self intersection

    } else {
        refraction_dir = normalize(normal + (ray.dir - normal) * (ior));  // TODO: Update with reflection direction
        ray.p0 = point + 0.001f *normal;  // offset point slightly to avoid self intersection
    }

    ray.W_wip = ray.W_wip;
    ray.dir = refraction_dir;
    ray.is_diffuse_bounce = false;
    ray.n_bounces++;
    return ray;

```

## I also have some hobbies, a big one of which is Photography.
### I have around 8 years of expirience in photography, with both landscapes and portraits under my belt. 
### My primary interest in that domain is Infrared landscape Photography now, after dabling in infrared film.
### What I've learned is that the quote:
> Your first 10,000 photographs are your worst 
### is incorrect in fact but correct in spirit. I improved the most by taking wayyy more photos than I needed to. (10,000 is a pretty accurate order of magnitude).
### But there is an element of rng that can't be ignored. there are plenty photos I've taken after my first 10,000 that are much worse than the cream of the crop from my first 10,000

[Back to the top](#about-me)