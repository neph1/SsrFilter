# SsrFilter
Stand alone SSR filter for jMonkeyEngine3

Based on the work of https://github.com/riccardobl


Essentially same as in this PR: https://github.com/jMonkeyEngine/jmonkeyengine/pull/1144

I thought this might be an easier way for people to get the filter and improve it.

You need this in your PBRLighting.j3md:

    Technique PreNormalGlossPass {

        VertexShader GLSL100 :   MatDefs/normal_gloss.vert
        FragmentShader GLSL100 : MatDefs/normal_gloss.frag

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

Demo here:

https://youtu.be/YxgEYg1D06Y
