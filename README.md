# Kaldi Native FBank Rust Bindings

Minimal bindings for [kaldi-native-fbank](https://github.com/csukuangfj/kaldi-native-fbank).

Still WIP. Only bound the things I needed.

Example: 

```rs
let mut fbank = OnlineFbank::new(16_000f32);
fbank.accept_waveform(16_000f32, &[0.0; 16000 * 10]);
fbank.input_finished();
let frame = fbank.get_frame(0);
// Use frame/features
```

## Notes

Generate bindings using [bindgen][bindgen] like this:

```sh
bindgen kaldi-native-fbank/kaldi-native-fbank/c-api/c-api.h -o src/lib_sys.rs
```

## TODO:

- [ ] Expose all the options needed

## License

MIT or Apache 2

[bindgen]: https://rust-lang.github.io/rust-bindgen/command-line-usage.html
