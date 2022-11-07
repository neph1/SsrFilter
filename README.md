# SsrFilter
Stand alone SSR filter for jMonkeyEngine3

![ssr](https://user-images.githubusercontent.com/7988802/200411755-8c770be4-4afe-402f-accc-e58087a67f84.gif)

https://youtu.be/YxgEYg1D06Y

Based on https://github.com/riccardobl/SimpleSSRShader

Gradle:

    repositories {
			...
			maven { url 'https://jitpack.io' }
	}
    dependencies {
	        implementation 'com.github.neph1:SsrFilter:Tag'
    }



It's dependent on a PreNormalGloss pass defined in PBRLighting.j3md:

    Technique PreNormalGlossPass {

        VertexShader GLSL100 :   MatDefs/SSR/normal_gloss.vert
        FragmentShader GLSL100 : MatDefs/SSR/normal_gloss.frag

        WorldParameters {
            WorldViewProjectionMatrix
            WorldViewMatrix
            WorldMatrix
            NormalMatrix
            ViewProjectionMatrix
            ViewMatrix
        }

        Defines {
            NUM_BONES : NumberOfBones
            INSTANCING : UseInstancing
            NUM_MORPH_TARGETS: NumberOfMorphTargets
            NUM_TARGETS_BUFFERS: NumberOfTargetsBuffers
            NORMALMAP : NormalMap
            ROUGHNESSMAP : RoughnessMap
            SPECGLOSSPIPELINE : UseSpecGloss
            GLOSSINESSMAP : GlossinessMap
        }

    }

I didn't want to include the whole modified PBRLighting due to possible conflicts(?).

