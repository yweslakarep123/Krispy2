# Krispy2

## Colab inference + video export
After training and saving `fql_best.pt`, run this in Colab (same runtime where `project_final.ipynb` code is loaded):

```python
# Evaluate checkpoint
metrics = load_and_eval('./checkpoints/fql_best.pt', n_eps=5)
print(metrics)

# Save one rollout video
out = eval_and_save_video(
    ckpt_path='./checkpoints/fql_best.pt',
    video_path='franka_eval.mp4',
    max_steps=280,
    seed=123,
    fps=20,
)
print(out)

# Optional: display in Colab
from IPython.display import Video
Video('franka_eval.mp4', embed=True)
```
