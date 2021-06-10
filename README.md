# WebPack loader to convert an audio file to a different format

It requires ffmpeg to be installed

## Install

```
npm i convert-audio-loader
```

## Use

In the WebPack config, add the loader and configure what extension you want the audio:

```
{
  test: /\.wav$/,
  use: [
    {
      loader: require.resolve('file-loader'),
    },
    {
      loader: "convert-audio-loader",
      options: {
        extension: "mp3",
      }
    },
  ],
},
```

Note that the loader gets an audio file and outputs the wav directly without emitting files. **It is intended to be used with other loaders** that write the audio and emit it. (such as the file-loader)

## Configuration

You can set 1 value:

* ```extension```: The target extension
