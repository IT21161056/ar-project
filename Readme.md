✅ **Option 1: Using gltf-transform (Recommended)**

```bash
# Step 1: Install gltf-transform CLI
npm install -g @gltf-transform/cli

# Step 2: Combine to .glb
gltf-transform copy scene.gltf scene.glb
```

This will:
- Embed the scene.bin  
- Embed all textures  
- Output a single .glb file
