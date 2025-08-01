# Custom MoonTV Deployment

This is a fork of [senshinya/MoonTV](https://github.com/senshinya/MoonTV) with custom configurations for local deployment.

## Features

- ✅ **Data Persistence**: Redis data is persisted in `./redis-data/` directory
- ✅ **Local Network Access**: Accessible from other devices on your local network
- ✅ **Auto-Sync**: Automatically syncs with upstream repository daily
- ✅ **Custom Configuration**: Preserves your custom docker-compose.yml settings

## Quick Start

1. **Clone this repository:**
   ```bash
   git clone https://github.com/billv5w/MoonTV.git
   cd MoonTV
   ```

2. **Start the services:**
   ```bash
   docker-compose up -d
   ```

3. **Access the application:**
   - Local: http://localhost:3000
   - Network: http://YOUR_LOCAL_IP:3000
   - Login: admin / admin_password

## Configuration

### Current Settings
- **Username**: admin
- **Password**: admin_password
- **Storage**: Redis with persistence
- **Network**: Accessible from local network
- **Registration**: Enabled

### Data Persistence
- Redis data is stored in `./redis-data/` directory
- Data survives container restarts and updates
- Backup this directory to preserve your data

### Customization
To modify settings, edit the `docker-compose.yml` file:
- Change credentials in environment variables
- Modify port mappings
- Add custom volumes or configurations

## Auto-Sync with Upstream

This fork automatically syncs with the original repository:
- **Schedule**: Daily at 2 AM UTC
- **Manual Trigger**: Available in GitHub Actions tab
- **Conflict Handling**: Preserves your custom docker-compose.yml

## Updating

### Automatic Updates
The repository automatically pulls updates from the upstream project while preserving your custom configurations.

### Manual Updates
```bash
git fetch upstream
git merge upstream/main
# Resolve any conflicts if needed
git push origin main
```

## Troubleshooting

### Services not starting
```bash
docker-compose logs
```

### Reset data
```bash
docker-compose down
rm -rf redis-data
docker-compose up -d
```

### Check service status
```bash
docker-compose ps
```

## Original Documentation

For complete documentation, see the [original MoonTV repository](https://github.com/senshinya/MoonTV).
