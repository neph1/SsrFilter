# SsrFilter
Stand alone SSR filter for jMonkeyEngine3

Based on https://github.com/riccardobl/SimpleSSRShader


Essentially same as in this PR: https://github.com/jMonkeyEngine/jmonkeyengine/pull/1144

I thought this might be an easier way for people to get the filter and improve it.

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

Demo here:

https://youtu.be/YxgEYg1D06Y
